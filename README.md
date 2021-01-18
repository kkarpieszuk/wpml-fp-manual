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

## Use Obj::prop() instead of obtaining directly

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

