# learning-rust
Document my rust learning curve
https://github.com/christophe-hubert/learning-rust

Game of life : first projet RUST+WASM
===

Based on 

https://rustwasm.github.io/docs/book/game-of-life/introduction.html  




Install NVM + latest node
---

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.6/install.sh | bash
source ~/.zshrc
nvm -v
nvm install node
node -v
nvm use 23
nvm install 23
npm install npm@latest -g
npm -v
npm install webpack -g
npm install webpack-cli -g
npm install webpack-dev-server -g

```

```
vi ~/.zshrc
```
```
export NODE_OPTIONS=--openssl-legacy-provider
nvm use 23
```
```
source ~/.zshrc
```

Install wasm-pack
---
```
curl https://wasm-bindgen.github.io/wasm-pack/installer/init.sh -sSf | sh
```
or (may be better to be align with the rustc version)
```
cargo install wasm-pack
```

To list all globally instally installed crates : 
```
cargo install --list
```
or 
```
ls ~/.cargo/bin/
```

version of installed wasm-bindgen
---
```
wasm-bindgen -V
```
Note the version of wasm-bindgen installed : to be used later in Cargo.toml
wasm-bindgen 0.2.126





Install the project 
https://github.com/cargo-generate/cargo-generate

```
cargo install cargo-generate
cargo generate --git https://github.com/rustwasm/wasm-pack-template
```

Enter Project :  Name wasm-game-of-life  

Edit Cargo.toml   
Be sure to update the version of wasm-bindgen to the latest stable version


```
[dependencies]
wasm-bindgen = "0.2.126"
...
[dev-dependencies]
wasm-bindgen-test = "0.3.76"
```


Build the Project : Generate the WASM and the npm package ./pkg
---
https://rustwasm.github.io/docs/book/game-of-life/hello-world.html#build-the-project

```
wasm-pack build
```


Putting it into a Web Page  
---
https://rustwasm.github.io/docs/book/game-of-life/hello-world.html#putting-it-into-a-web-page


```
npm init wasm-app www
cd www
npm install
```


Serving Locally
---
https://rustwasm.github.io/docs/book/game-of-life/hello-world.html#serving-locally

```
cd www
npm run start
```
