<?php
    session_start(); 
    echo "sdljds";

    function is_session_started()
    {
        if ( php_sapi_name() !== 'cli' ) {
            if ( version_compare(phpversion(), '5.4.0', '>=') ) {
                return session_status() === PHP_SESSION_ACTIVE ? TRUE : FALSE;
            } else {
                return session_id() === '' ? FALSE : TRUE;
            }
        } 
        return FALSE; 
    }
    $session_status = is_session_started();
    //$Lemon = FALSE;
    echo $Lemon;
    echo $session_status;

    if ( is_session_started() === FALSE ) session_start();

    if(session_id() == '') {
        echo "hasn't started";
    }
    else 
    echo "Session started";

    //$_SESSION
    
    $_SESSION["favcolor"] = "Red";
    $_SESSION["Visit No."] += 1;
    print_r($_SESSION);


    /*
    Useful session stuff - 
    session_destroy(); // sessions stay if you change the document etc. Different browser seems to work


    //property_exists(object, property)
    */

?>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="styles.css">
    <link href='http://fonts.googleapis.com/css?family=Droid+Sans' rel='stylesheet' type='text/css'>
    <link href='https://fonts.googleapis.com/css?family=Xanh+Mono' rel='stylesheet' type='text/css'>
    <link href='https://fonts.googleapis.com/css?family=Xanh+Mono' rel='stylesheet' type='text/css'>
    <link href="https://fonts.googleapis.com/css?family=Playfair+Display:400,700,700i|Source+Sans+Pro" rel="stylesheet">
    
    <title>BirthHud</title>
</head>
<body>
    <div class="main_body">
        <img class="Logo" src= "BirthWebLogo.png" alt="">
          
        <div class="navigation">
            <a href="#about">Home</a>
            <a href="#about">Social</a>
            <a href="#about">Booty</a>
            <a href="#about">Animations</a>
            <a href="#about">Social</a>
        </div>

        

        <div class="text">
            <p>
                &#8220 Lorem, ipsum dolor sit amet consectetur adipisicing elit. Iusto praesentium non adipisci ducimus quasi itaque ipsum reprehenderit perspiciatis, ut odio maiores dolorem in dolores, assumenda veritatis cupiditate eveniet. Tempore, ea?
            </p>
            <p>
                Lorem, ipsum dolor sit amet consectetur adipisicing elit. Iusto praesentium non adipisci ducimus quasi itaque ipsum reprehenderit perspiciatis, ut odio maiores dolorem in dolores, assumenda veritatis cupiditate eveniet. Tempore, ea?
            </p>
        </div>
  
        <div class="buttons">

            <button id="1">Poses</button>
            <button>Booty</button>
            <button>Boobs</button>
            <button>CLICKME</button>
            <button>CLICKME</button>
            <button>CLICKME</button>
            <button>CLICKME</button>
        </div> 

        <div class="buttons2"> 

            <button id="1">Poses</button>
        </div>


        
       

        <div class="Test2">
            <img class= "I1" src="https://images.unsplash.com/photo-1514539079130-25950c84af65?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&w=1000&q=80" alt="">
            <img class= "I2" src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRssmDW2CkJ_LhiK-g-aTWeJkTYuwzRnsia8g&usqp=CAU" alt="">
            <img id="3" src="https://images.unsplash.com/photo-1510218830377-2e994ea9087d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&w=1000&q=80" alt="">
            <img src="https://images.unsplash.com/photo-1514539079130-25950c84af65?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&w=1000&q=80" alt="">
        </div>

        <div class="Test1"></div>
 
        <script>

            let p = document.createElement("p");
            p.innerHTML = "sdlfjsdflkjdslkjdsfkljds";
            document.body.appendChild(p);

            //let button_1  = document.getElementById("1");
            document.getElementById("1").onclick = function()
            {
                console.log("clicked!!");

            }



            // https://www.mikestreety.co.uk/blog/how-to-use-fetch-in-javascript-to-get-or-post-data
            
            
            /*
            fetch(url_php_old, {  
                method: 'post',
                body: JSON.stringify(data)
            }).then(data => {
                if (!data.ok) {
                throw new Error('Network response was not ok');
                }
                
                else
                console.log("success");

                // data is anything returned by your API/backend code
                console.log("returned whoot!");
                console.log(data);
                //console.log('Success:', data);
            });
            */
            
            /*
            fetch(url_php_old, {  
                method: 'post',
                body: JSON.stringify(data)
            })
            .then(res => res.json()) 
            .then(response => console.log('Success:', JSON.stringify(response)))
            .catch(error => console.error('Error:',error))
            */

            let data = {
                Fruit: "Apple"
            };
 
            var url_php_old = "http://mrfry.dreamhosters.com/SLTests/Website_Hud/Echoback.php";
            //works to SL!!!!
            

            fetch(url_php_old, {  
                method: 'post',
                body: JSON.stringify(data)
            })
            .then(res => res.json()) 
            .then(function(response){
                    console.log('Success:2', JSON.stringify(response));
                } 
            )
            .catch(error => console.error('Error:',error))
                
            // above as function
            let fetch_php = function(php_url,object_data){
                fetch(php_url, {  
                method: 'post',
                body: JSON.stringify(object_data)
                })
                .then(res => res.json()) 
                .then(function(response){
                        console.log('Success:3', JSON.stringify(response));
                    } 
                )
                .catch(error => console.error('Error:',error))
            }

            fetch_php(url_php_old,data);

            /*
            var f = fetch(url_php_old, {  
                method: 'post',
                body: JSON.stringify(data)
            });
            //f.then(response => response.json());
 
            //fetch_SL("sdfsdfdsfdsfd");
            */

            var SL_tempPrim_url = "http://simhost-0c673f4bbdc25eeb3.agni.secondlife.io:12046/cap/e077f11b-723e-b2ee-f31e-1e1f6c7a199f";

            var fetch_SL = function(data){
                fetch(SL_tempPrim_url, {  
                method: 'post',
                body: JSON.stringify(data)
                });
                //LSL request limit - "The viewer limits permission requests from any agent to any other agent to 5 dialogs in 10 seconds."
            }
            // BUTTON CLICK 
            document.getElementById("1").onclick = function()
            {
                fetch_SL("sdfsdfdsfdsfd");
            }

            //document.write("sdlkfjsd");

            console.log ("sdgljdsfkldjsfkldsjflkjdsfkljsdlkfjds");
            
            var timer_test = function(words) {
                console.log (words);
            }

            timer_test("hi there");
            /*
            setInterval(function(){
                console.log ("things");
                fetch_php(url_php_old,data);
            }, 100); 
            */

            /*
            var myVar = setInterval(myTimer, 1000);

            function myTimer() {
            var d = new Date();
            console.log ( d.toLocaleTimeString() );
            }
            */

            let ba = document.createElement("p");// gets a whole array of them
            document.body.appendChild(ba); 
            
            //var butDiv = document.getElementsByClassName("buttons2");// gets a whole array of them

            
            var butDi = document.querySelector(".buttons2"); 
            console.log(butDi);
              
             var btn = document.createElement("BUTTON");  
            btn.innerHTML = "Tester";

            document.body.appendChild(btn);
 



            var i; 
            for (i = 0; i < 25; i++) {
                var bu = document.createElement("BUTTON");  
                bu.innerHTML = i;
                bu.id = i;
                bu.classList.add("TesterButtons");
                butDi.appendChild(bu);
            }

            var x_array = ["stuff","no",2,24,232,32,2,2,32,];
            console.log(x_array);
            
            var b222 = document.getElementsByClassName("TesterButtons");
            console.log(b222);

        </script>



    </div>
    
</body>
</html>
