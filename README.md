# Vue.js truffle box

A [`truffle box`](http://truffleframework.com/boxes/) to serve as the foundation of any [`Truffle`](http://truffleframework.com) and [`Vue.js`](https://vuejs.org/) dApp. Comes with [`Vue.js`](https://vuejs.org/), [`vue-router`](https://router.vuejs.org/en/), [`Vuex`](https://vuex.vuejs.org/en/intro.html), [`sass-loader`](https://github.com/webpack-contrib/sass-loader) and [`Vuetify`](https://github.com/vuetifyjs/vuetify)
. A minimalist user authentication smart contract is also provided.

## Installation

1. Install [Truffle](http://truffleframework.com) and an Ethereum client - like [Ganache CLI](https://github.com/trufflesuite/ganache-cli).
	```
	npm install -g truffle // Version 3.0.5+ required.
	npm install -g ganache-cli
	```

2. Download this box.
	```
	truffle unbox filipesoccol/truffle-vuetify
	```
3. Launch [`ganache-cli`](https://github.com/ethereumjs/testrpc).
	```
	ganache-cli <options>
	```

4. Compile and migrate the contracts.
	```
	truffle compile
	truffle migrate
	```

4. Run the webpack server for front-end hot reloading. Smart contract changes do not support hot reloading for now.
	```
	npm run start
	```
    
## Tests
This box comes with everything bundled for `unit`, `e2e` and `truffle` contracts testing.

1. `unit` and `e2e` tests.
	```
	npm run test/dapp
	```

2. `truffle` contracts tests.
	```
	npm run test/truffle
	```

3. Alternatively you can directly run `unit`, `e2e` and `truffle` contracts tests in one command.
	```
	npm run test
	```

## Build for production
To build the application for production, use the build command. A production build will be compiled in the `dist` folder.
```javascript
npm run build
```

## Issues

Please send any bug issues or proposal for improvement to [Issues](https://github.com/filipesoccol/truffle-vuetify/issues).