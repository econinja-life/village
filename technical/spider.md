## Goals
- Be declarative by default, optionally imperative (by direct scripts)
- NOT Active Record Model, but Object Persistence Model
- Documents = Resources
- Graphs are Documents with Connections
- Be usable with multiple language processors, et all (only develop neo4j though)
- Allow for different `Response`s
- Include three levels of queries
  - Document Queries (may convert to traversal for neo4j backends)
  - Relationship Queries (Simple handling of things like joins (1 level deep))
  - Traversals (Graph Only)

## Code
```php
<?php
// Higher Level Repository
$repo = new ProductManager();

$product = $repo->findByUpc($upc); // And other high level methods
$product->setSomething('new');

// Also includes a couple basic ones
$id = $repo->create([]);
$product = $repo->findWhere('something', '=', 'something');
$repo->query($query);

// And, to keep in line with solid, maybe the high level ones are actually just query classes with a __call()
$product = $repo->findBySomeCoolThing($one, $two);
$query - new FindBySomeCoolThing($one, $two);
return $repo->find($query);

$repo->save($product);

/* More Basic */
// Get the connection (which holds a driver, which holds language processor(s))
$connection = Connections::get('neo4j', $override_options);
$connection = Connections::make($options);

// Query the object
// Using a generic query builder (can be traversals as well)
$response = Spider\Queries\Query($connection)
    ->select()
    ->from('label')
    ->where('something', 'else')
    ->andWhere('something', '=', 'other')
    ->orderBy('something')
    ->limit(3)
    ->getAsSet();
    
// Or a specific script
$response = Spider\Queries\Cypher($connection)
    ->match()
    ->return();
    
// Or a graph traversal (mimic gremlin or cypher)
$respons = Spider\Queries\Traversal($connection)
    ->i()->dont()->know()
    ->getShortestPath;
    
// Build an EcoNinja Resource and modify it
$product = EcoNinja\Resources\Product::from($response); // Extends Document, DocumentCollection, or Graph
$product->setSomething('my new something');

// And all done
$connection->update($product); // exception if not created
$connection->create($product);
$connection->upsert($product);
$connection->drop($product);

$connection->findOrCreate($product|$id|$query);

$connection->command($language_script_or_to_string_builder); // Read or write
$connection->query(); // Read only
$connection->script($type, $gremlin); // Extensible and controlled by connections

// Transactions
$connection->transaction(callable|Transaction function($connection, $transaction) {
    $transaction->push('name')->update();
    $transaction->push('othername')->create();
    
    return $transaction;
})
->commit();
```