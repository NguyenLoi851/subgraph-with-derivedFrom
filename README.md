# create-basic-subgraph

Note:

- Click pending subgraph in The Graph website to see to lastest deploy version
- Example in file schema.graphql

Type A{
- p1: BigInt
- p2: String
- p3: B
}

Type B{
- p4: BigInt
- p5: BigInt
}

>> In file mapping.js, we should declare p3 in A like this:

let entity = A.load(id)
entity.p3 = ID of B

>> If using @derivedFrom like this:

Type B{
- p4: BigInt
- p5: BigInt
- p6: A @derivedFrom(field: "p3")
}

>> We don't need to declare p6 of B
