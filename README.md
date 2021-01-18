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

## Use Obj::keys instead of array_keys

Instead of:
```
$data [
  'foo' => 'bar'
];
array_keys( $data );
```
write:
```
$data [
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
