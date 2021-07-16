# wpml-fp-manual

Non official WPML Functional Programming Library manual

Repository url: https://git.onthegosystems.com/wpml-packages/fp

## Installation

`composer require wpml/fp`

## Use Fns::each() in place of foreach

Instead of writing:

```
$someArray = [ 1, 2, 3 ];
foreach ( $someArray as &$val ) {
  $val++;
} 
```

write:

```
$someArray = [ 1, 2, 3 ];

$someArray = Fns::each( function( $val ) {
  return $val++;
}, $someArray );
```

## Use Obj::prop() instead of obtaining properties directly

Instead of:

```
$data = [
  'foo' => 'bar'
];

$data['foo'];
```


write:

```
$data = [
  'foo' => 'bar'
];

Obj::prop( 'foo', $data ); 
```

The advantage is, you don't need to know if `$data` is array or object. It will work with any data structure:

```
$data = new stdClass();
$data->foo = 'bar';

Obj::prop( 'foo', $data ); // the same as above
```

## Use Obj::pathOr to get default value or value from nested structure

If you have an array like this:
```
$data = [
  'foo' => [
    'bar' => 'baz'
  ]
];
```
and you wnat to obtain `baz` you can use:
```
$value = Obj::pathOr( 'not found', [ 'foo', 'bar' ], $data ); // returns 'baz'
```
if the element on path does not exist, the first argument will be returned:
```
$value = Obj::pathOr( 'not found', [ 'foo', 'bal' ], $data ); // returns 'not found'
```


## Use Obj::keys instead of array_keys

Instead of:
```
$data = [
  'foo' => 'bar'
];
array_keys( $data );
```
write:
```
$data = [
  'foo' => 'bar'
];
Obj::keys( $data ); // returns [ 'foo' ]
```

You can obtain public object properties in the same way:
```
$data = new stdClass();
$data->foo = 'bar';

Obj::keys( $data ); // returns [ 'foo' ]
```

## Use pipe() for ordered execution

You can chain functions to be executed from left to right with `pipe()`.

Instead of writing:
```
$data = [
  'foo' => [
    'bar' => 'baz'
  ]
];

Fns::each( 'strtoupper', Fns::keys( Fns::prop( 'foo', $data ) ) );
```
write:
```
$data = [
  'foo' => [
    'bar' => 'baz'
  ]
];
$screamBar = pipe( Fns::prop( 'foo' ), Fns::keys()  );

Fns::each( 'strtoupper', $screamBar( $data ) );
```

Notice this time function in pipe does not take processed data as a second argument. Data comes from:
- first from function call with $data as argument (`$screamBar( $data )`)
- then data is passed from left to the right throught the pipe. So `Fns::prop( 'foo' )` gets data from function call above, then it runs actions on it and what it returns, goes to the next function (`Fns::keys()` gets the result of `Fns::prop( 'foo' )` which is `[ 'bar' => 'baz' ]`)
