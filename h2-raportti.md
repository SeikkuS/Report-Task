h2 komentaja Pingviini

1. Aloitin lataamalla micron laittamalla terminaaliin: 

       $ curl https://getmic.ro | bash

2. Tämän jälkeen koitin katsoa raudan, mutta minulla ei ollut lshw asennettuna, joten ensin latasin sen.

       $ sudo apt-get install lshw
       $ sudo lshw -short -sanitize
       
3. ![kuva](https://user-images.githubusercontent.com/105205141/213909443-a8d0ead2-b005-4713-a4e2-1f7240b875de.png)

