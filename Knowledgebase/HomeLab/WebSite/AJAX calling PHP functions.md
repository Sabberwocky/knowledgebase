this will explain how to call a function in php from ajax


define generic junktion in php
```php
if(isset($_POST['functionname'])) {
    $functionname = $_POST['functionname'];
    if(function_exists($functionname)) {
        
        if(!isset($_POST['arguments'])){ #checks if arguments are passed
            call_user_func($functionname); #calls function without arguments
        }else {
            $arguments = $_POST['arguments'];
            $reflector = new ReflectionFunction($functionname);
            $number_of_arguments = $reflector->getNumberOfParameters();
            call_user_func_array($functionname, array_slice($arguments, 0, $number_of_arguments)); #calls function with a flexible amount of arguments
        }
    }
}
```

example functions to be called:
```php
function ajaxCallNoArg(){
    
    error_log("call ajaxCallNoArg");
    echo "end ajaxCallNoArg";
}

function ajaxCallSingleArg($msgc){
    
    error_log($msgc);
    error_log("this is ajaxCallSingleArg");
    echo "end ajaxCallSingleArg";
}

function ajaxCallMultiArg($msg1,$msg2,$msg3) {
    
    error_log("this is ajaxCallMultiArg");
    error_log($msg1);
    error_log($msg2);
    error_log($msg3);
    if (!isset($msg1)|| !isset($msg2) ||!isset($msg3)) {
        error_log("error: one of the arguments is not set");
        return;
    }
    echo "end ajaxCallMultiArg";
}
```

The following AJAX will call the php functions from JS
```js
$(document).ready(function() {
    document.getElementById("examplebutton").addEventListener("click", function(event) {
        $.ajax({
			type: "POST",
			url: "noteHandling.php",
			data: { functionname: "ajaxCallNoArg"},
			success: function (data) {
				console.log(data);
			}
		});

		$.ajax({
			type: "POST",
			url: "noteHandling.php",
			dataType: "html",
			data: { functionname: "ajaxCallSingleArg", arguments: ["only one message"] },
			success: function (data) {
				console.log(data);
			}
		});

		$.ajax({
			type: "POST",
			url: "noteHandling.php",
			data: { functionname: "ajaxCallMultiArg", arguments: ["first message", "second message", "third message"] },
			success: function (data) {
				console.log(data);
			}
		});

	});
});
```

send an array as argument with AJAX:
```javascript
$.ajax({
                        type: "POST",
                        url: "note.handling.php",
                        data: { functionname: "addNote", arguments: ["createn from AJAX", "second message", ["task","note"]] },
                        success: function (data) {
                            console.log(data);
                        }
                    });
```
