const response = await fetch('https://api.mainnet-beta.solana.com', {

method: 'POST',

headers: {

'Content-Type': 'application/json',

},

body: JSON.stringify({

"jsonrpc": "2.0",

"id": 1,

"method": "getSignaturesForAddress",

"params": [

"qudoGprpXXPMwV2TaVgwWbPD7c2GBydfoc6AUr4oWmq",

{

"limit": 100

}

]

}),

});