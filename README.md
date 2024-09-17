#responsive

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css" integrity="sha512-Kc323vGBEqzTmouAECnVceyQqyqdsSiqLQISBL29aUW4U/M7pSPA/gEUZQqv1cwx4OnYxTxve5UMg5GT6L4JJg==" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <title>responsive navbar</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <div class="navbar">
            <div class="logo"><a href="#">Web Dev Creative</a></div>
        <ul class="links">
            <li><a href="hero">Home</a></li>
            <li><a href="about">About</a></li>
            <li><a href="service">Service</a></li>
            <li><a href="contact">Contact</a></li>
        </ul>
        <a href="#" class="action_btn">Get Started</a>
        <div class="toggle_btn">
            <i class="fa-solid fa-bars"></i> 
        </div>
        </div>

        <div class="dropdown_menu">
            <li><a href="hero">Home</a></li>
            <li><a href="about">About</a></li>
            <li><a href="service">Service</a></li>
            <li><a href="contact">Contact</a></li>
            <li><a href="#" class="action_btn">Get Started</a></li>
        </div>
    </header>
        <section id="hero">
            <h1>WelCome</h1>
            <p>Lorem ipsum dolor sit amet <br>
         consectetur adipisicing elit. Enim, voluptates.</p>
        </section>
    <main></main>

    <script>
        const togglebtn = document.querySelector('.toggle_btn')
        const toggleBtnIcon = document.querySelector('.toggle_btn i')
        const DropDownMenu = document.querySelector('.Dropdown_menu')

        togglebtn.onclick = function() {
            DropDownMenu.classList.toggle('open')
            const isOpen = DropDownMenu.classlist.contais('open')

            toggleBtnIcon.classlist = isopen
            ? 'fa-solid fa-xmark'
            : 'fa-solid fa-bars'
        }  
    </script>
</body>
</html>

/** css **/

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

body{
    height: 100vh;
    background-color: #000;
    background-image: url('https://th.bing.com/th/id/R.e29103faad6c8164a3940007306876c3?rik=5hnZ6oFoGOn7eQ&riu=http%3a%2f%2fimages.unsplash.com%2fphoto-1566264956500-0549ed17e161%3fixlib%3drb-1.2.1%26q%3d80%26fm%3djpg%26crop%3dentropy%26cs%3dtinysrgb%26w%3d1080%26fit%3dmax%26ixid%3deyJhcHBfaWQiOjEyMDd9&ehk=Eq%2f3gtVGbPQAVHyWOxG%2b3tGILLT1DLgCih2a8FfZM74%3d&risl=&pid=ImgRaw&r=0');
    background-size: cover;
    background-position: center;
}

li{
    list-style: none;
}

a{
    text-decoration: none;
    color: white;
    font-size: 1rem;
}

a:hover{
    color: orange;
}

/**  header  **/

header{
    position: relative;
    padding: 0.2rem;
}

.navbar{
    width: 100%;
    height: 60px;
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.navbar .logo a {
    font-size: 1.5rem;
    font-weight: bold;
}

.navbar .links {
    display: flex;
    gap: 2rem;
}

.navbar .toggle_btn{
    color: #fff;
    font-size: 1.5rem;
    cursor: pointer;
    display: none;
}

.action_btn{
    background-color: orange;
    color: white;
    padding: 0.5rem 1rem;
    border: none;
    outline: none;
    border-radius: 20px;
    font-size: 0.8rem;
    font-weight: bold;
    cursor: pointer;
    transition: scale 0.2ease;
}

.action_btn:hover{
    scale: 1.05;
    color: #fff;
}

.action_btn:active{
    scale: 0.95;
}

/** dropdown menu **/

.dropdown_menu{
    display: none;
    position: absolute;
    right: 2rem;
    top: 60px;
    width: 300px;
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter :blur(15px);
    border-radius: 10px;
    overflow: hidden;
    transition: height 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.dropdown_menu.open{
    height: 240px;
}

.dropdown_menu li{
    padding: 0.7rem;
    display: flex;
    align-items: center;
    justify-content: center;
}

.dropdown_menu .action_btn{
    width: 100%;
    display: flex;
    justify-content: center;
}

/** hro section **/

section#hero{
    height:calc(100vh - 60px) ;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: white;
}

#hero h1{
    font-size: 3rem;
    margin-bottom: 1rem;
}

/** responsive design **/

@media (max-width: 992px) {
    .navbar .links,
    .navbar .action_btn{
        display: none;
    }

    .navbar .toggle_btn{
        display: block;
    }

    .dropdown_menu{
        display: block;
    }

}

@media (max-width: 576px) {
    .dropdown_menu{
        left: 2rem;
        width: unset;
    }
}


