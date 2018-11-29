RBTokens is a login plugin for partners of [rbdigital](http://rbdigital.rbdigital.com/)

* DEMO: [EDIT IN CODEPEN](https://codepen.io/dongfang_mao/pen/zMmWxY)


## Download and include
```
<script src="rbtokens.min.js"></script>
```

## Install from [npm](https://www.npmjs.com/package/rbtokens)
```
npm install --save rbtokens
```

## API docs
- `config(settings)`

   ```js
      RBTokens.config({
      env: "qa",                            // optional, could be "qa", "stage", "uat" or "prod". default is "prod"
      libraryId: "3925",                    // required
      token: "BF8DD41C-B286-4F60-9FF5-F4C5B3E57A11", // required 
      region: "NA",                         // required, could be "NA" or "EU"
      width: "400px",                       // optional 
      template: {                           // optional  
        id: "container",                    // required 
          title: {                          // optional
            text: "Long into Your Account", // optional
            fontSize: "25px",               // optional
            color: "#802754",               // optional
            fontWeight: "700"               // optional
        },
        labels: {                           // optional
            indentifier: "LIBRARYCARD",     // optional
            secret: "PIN",                  // optional
            fontSize: "14px",               // optional
            color: "#48494A",               // optional
            fontWeight: "600",              // optional
        },
        button: {
            text: "Log In",                 // optional
            fontSize: "16px",               // optional
            color: "#fff",                  // optional
            fontWeight: "600",              // optional
            backgroundColor: "#00a19b",     // optional
            click : function (event, username, password) {   // optional, click event handler 
		    RBTokens.loginAndRedirect({ "email": "jaswinder.singh0011@gmail.com"}).then(function(data){
			console.log(data);
		    }).catch(function(err){
			console.log(err);
		    });
            },
        },
      }
    });
  ```
- `login(indentifier)` indentifier could be username, email or librarycard
   ```js
    RBTokens.login({ "email": "jaswinder.singh0011@gmail.com"}).then(function(data){
	
    }).catch(function(err){

    });
   ```
- `loginAndRedirect(indentifier)` same to `login()` except it will redirect to rbdigital with bear token
   ```js
    RBTokens.loginAndRedirect({ "email": "jaswinder.singh0011@gmail.com"}).then(function(data){
	
    }).catch(function(err){

    });
   ```
- `register(userinfo)` userinfo is an object with user information
   ```js
    RBTokens.register(userinfo).then(function(data){
	
    }).catch(function(err){

    });
   ```
- `registerAndRedirect(userinfo)` same to `register(userinfo)` except it will redirect to rbdigital with bear token
   ```js
    RBTokens.registerAndRedirect(userinfo).then(function(data){
	
    }).catch(function(err){

    });
   ```
