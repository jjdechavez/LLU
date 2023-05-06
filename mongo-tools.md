
MongoImport to import file on mongodb:
`mongoimport --mode=upsert --db=ecommerece-graph --collection=products --file=products.json`

MongoExport to export a file from mongodb:
`mongoexport --collection=products --db=ecommerece-graph --out=products.json`
