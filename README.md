## simple-promises-polyfill

        function asyncFn(){
          var success = function(c){};
          var error = function(c){};
          //Promise
    
          setTimeout(function(){
            success('async finished!');
          },2000);
    
          //Promise
            return {
                then: function(cb) {
                    success = cb;
                    return this;
                },
                error: function(cb) {
                    error = cb;
                    return this;
                }
            };
        }
        
        asyncFn().then(function(){
          console.log('I\'m done!');
        });
