# Queries

## Retrieves the first ten Azuki transfers

query {
  transfers(first: 10) {
    id
    from
    to
    tokenId
    blockTimestamp
  }
}

## Retrieves the first five record approvals and bulk approvals

query {
  approvals(first: 5) {
    id
    owner
    approved
    tokenId
  }
  approvalForAlls(first: 5) {
    id
    owner
    operator
    approved
  }
}

## Retrieves the first five record bulk approvals for a specific owner

{
  approvalForAlls(where: {owner: "specific-owner-address"}, first: 5) {
    id
    owner
    operator
    approved
    blockNumber
    blockTimestamp
    transactionHash
  }
}

## Retrieves approvals within a specific block range

{
  approvals(where: {blockNumber_gte: "start-block-number", blockNumber_lte: "end-block-number"}, first: 10) {
    id
    owner
    approved
    tokenId
    blockNumber
    blockTimestamp
    transactionHash
  }
}
