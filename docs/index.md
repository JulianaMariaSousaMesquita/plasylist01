## Welcome to GitHub Pages


You can use the [editor on GitHub](https://github.com/JulianaMariaSousaMesquita/plasylist01/edit/main/docs/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
# Playlist index.html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <title></title>
        <meta name="description" content="">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="css/style.css">
        <script src="js/scripts.js"></script>
        <script src="js/jquery.min.js"></script>
    </head>
    <body>
<audio src="" controls id="audioPlayer">
        Sorry, your browser doesn't support html5!
    </audio>
    <ul id="playlist">
           <li class="active"><a href="/musicas/palcoiluminado_Meninafaceira.mp3">01. Menina Faceira</a></li>
           <li><a href="/musicas/palcoiluminado_Rainhadacocada.mp3" >02. Rainha da Cocada</a></li>
           <li><a href="/musicas/palcoiluminado_Amordecarnaval.mp3">03. Amor de Carnaval</a></li>
           <li><a href="/musicas/palcoiluminado_Alemdailusao.mp3">04. Além da Ilusão</a></li>
           <li><a href="/musicas/palcoiluminado_Tribunaldoamor.mp3">05. Tibunal do Amor</a></li>
           <li><a href="/musicas/palcoiluminado_Feranocio.mp3">06. Fera no Cio</a></li>
           <li><a href="/musicas/palcoiluminado_Peleesuor.mp3">07. Pele e suor</a></li>
           <li><a href="/musicas/palcoiluminado_Quemama.mp3">08. Quem amar</a></li>
           <li><a href="/musicas/palcoiluminado_Maisumgrandeamor.mp3">09. Mais um grande amor</a></li>
           <li><a href="/musicas/palcoiluminado_Fiodanavalha.mp3">10. Fio da navalhar</a></li>
    </ul>
    <script src="https://code.jquery.com/jquery-2.2.0.js"></script>
    <script src="audioPlayer.js"></script>
    <script>
        // loads the audio player
        audioPlayer();
    </script>
    </body>
</html>


# Playlist javascript.js
        function audioPlayer(){
            var currentSong = 0;
            $("#audioPlayer")[0].src = $("#playlist li a")[0];            
            $("#audioPlayer")[0].play();          
            $("#playlist li a").click(function(e){
               e.preventDefault();                
               $("#audioPlayer")[0].src = this;           
               $("#audioPlayer")[0].play();
               $("#playlist li").removeClass("current-song active");             
                currentSong = $(this).parent().index();
                $(this).parent().addClass("current-song active");                
            });
            
            $("#audioPlayer")[0].addEventListener("ended", function(){
                currentSong++;
                if(currentSong == $("#playlist li a").length)
                    currentSong = 0;
                $("#playlist li").removeClass("current-song active");
                $("#playlist li:eq("+currentSong+")").addClass("current-song active");
                $("#audioPlayer")[0].src = $("#playlist li a")[currentSong].href;
                $("#audioPlayer")[0].play();
            });
        }


# Playlist style.css

.playlist {
    align-items: center;
    font-family: "Century Gothic";
} 

ul   {
    list-style: none;
    padding: 0%;    
}

a  {
    text-decoration: none;
    color: #444;
}

li:hover  {
    background: #eee;
    border-bottom: solid 1px #f60;
}

li  {
    width: 20%;
    padding: 5px;
    border-bottom: solid 1px #ccc;
} 

.active a   {
    color: #f60;
    padding-left: 1px;
    font-style: italic;
}

```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/JulianaMariaSousaMesquita/plasylist01/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
