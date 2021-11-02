Fns
```
sitepress-multilingual-cms$ grep -oh -d recurse " Fns::[a-z]*(" * | sort | uniq -c | sort -r
     94  Fns::map(
     68  Fns::always(
     57  Fns::identity(
     34  Fns::tap(
     31  Fns::filter(
     27  Fns::converge(
     20  Fns::memorize(
     19  Fns::unary(
     12  Fns::reject(
     12  Fns::reduce(
      8  Fns::until(
      4  Fns::make(
      3  Fns::value(
      3  Fns::noop(
      2  Fns::once(
      2  Fns::maybe(
      2  Fns::either(
      2  Fns::each(
      2  Fns::ascend(
      1  Fns::safe(
      1  Fns::descend(
```
Obj
```
sitepress-multilingual-cms$ grep -oh -d recurse " Obj::[a-z]*(" * | sort | uniq -c | sort -r
    315  Obj::prop(
     55  Obj::path(
     39  Obj::keys(
     37  Obj::values(
     27  Obj::assoc(
     14  Obj::over(
      8  Obj::pick(
      7  Obj::view(
      5  Obj::without(
      5  Obj::set(
      5  Obj::has(
      4  Obj::props(
      4  Obj::evolve(
      2  Obj::where(
      2  Obj::project(
      2  Obj::lens(
```
Either
```
sitepress-multilingual-cms$ grep -oh -d recurse " Either::[a-z]*(" * | sort | uniq -c | sort -r
     90  Either::left(
     88  Either::of(
     62  Either::right(
```
Logic
```
sitepress-multilingual-cms$ grep -oh -d recurse " Logic::[a-z]*(" * | sort | uniq -c | sort -r
     14  Logic::not(
     14  Logic::both(
     13  Logic::complement(
      6  Logic::cond(
      1  Logic::when(
      1  Logic::until(
      1  Logic::unless(
      1  Logic::either(
```
Lst
```
sitepress-multilingual-cms$ grep -oh -d recurse " Lst::[a-z]*(" * | sort | uniq -c | sort -r
     55  Lst::includes(
     27  Lst::pluck(
     23  Lst::nth(
     21  Lst::concat(
     19  Lst::find(
     18  Lst::length(
     17  Lst::join(
     11  Lst::repeat(
      8  Lst::diff(
      8  Lst::append(
      7  Lst::last(
      6  Lst::xprod(
      6  Lst::insert(
      5  Lst::sort(
      5  Lst::range(
      5  Lst::make(
      5  Lst::drop(
      4  Lst::zip(
      4  Lst::slice(
      3  Lst::reverse(
      3  Lst::partition(
      3  Lst::flatten(
      2  Lst::take(
      1  Lst::unfold(
      1  Lst::prepend(
```
Math
```
sitepress-multilingual-cms$ grep -oh -d recurse " Math::[a-z]*(" * | sort | uniq -c | sort -r
      9  Math::add(
      7  Math::multiply(
      3  Math::product(
```
Maybe
```
sitepress-multilingual-cms$ grep -oh -d recurse " Maybe::[a-z]*(" * | sort | uniq -c | sort -r
     49  Maybe::of(
     21  Maybe::nothing(
      4  Maybe::just(
      1  Maybe::safe(
```
Relation
```
sitepress-multilingual-cms$ grep -oh -d recurse " Relation::[a-z]*(" * | sort | uniq -c | sort -r
     35  Relation::equals(
     30  Relation::gt(
     16  Relation::lt(
     16  Relation::gte(
     15  Relation::lte(
```
