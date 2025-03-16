<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Nimish Gupta</title>
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            document.querySelectorAll("nav a").forEach(anchor => {
                anchor.addEventListener("click", function(e) {
                    e.preventDefault();  
                    const targetId = this.getAttribute("href").substring(1);  
                    const targetElement = document.getElementById(targetId);  
                    if (targetElement) {
                        window.scrollTo({
                            top: targetElement.offsetTop - 50,
                            behavior: "smooth"
                        });
                    }
                });
            });
            const sections = document.querySelectorAll("section");
            const navLinks = document.querySelectorAll("nav a");
            window.addEventListener("scroll", () => {
                let scrollPosition = window.scrollY + 60;
                sections.forEach((section, index) => {
                    if (scrollPosition >= section.offsetTop && scrollPosition < section.offsetTop + section.offsetHeight) {
                        navLinks.forEach(link => link.classList.remove("active"));
                        navLinks[index].classList.add("active");
                    }
                });
            });
            document.querySelectorAll(".btn-primary").forEach(button => {
                button.addEventListener("mouseenter", () => {
                    button.style.transform = "scale(1.05)";
                });
                button.addEventListener("mouseleave", () => {
                    button.style.transform = "scale(1)";
                });
            });
        });
    </script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Poppins', sans-serif;
            background: #ffffff;
            color: #333;
            line-height: 1.6;
        }
        h1, h2, h3 {
            font-weight: 700;
        }
        .btn-primary {
            background: #007bff;
            color: #fff;
            padding: 12px 24px;
            border: none;
            border-radius: 2px;
            cursor: pointer;
            transition: transform 0.3s ease-in-out;
            font-size: 1rem;
            text-transform: uppercase;
        }
        .btn-primary:hover {
            background: #0056b3;
        }
        a {
            text-decoration: none;
            color: black;
        }
        a:hover {
            color: #007bff;
        }
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            text-align: center;
            padding: 20px 10%;
            background: #fff;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }
        .nav-links {
            list-style: none;
            display: flex;
            gap: 30px;
        }
        .nav-links li a {
            text-decoration: none;
            color: #333;
            font-weight: bold;
            font-size: 1rem;
            transition: 0.3s;
            padding: 10px;
        }
        nav ul li img {
            border-radius: 100px;
        }
        .nav-links li a:hover {
            color: #007bff;
        }
        #hero {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 120px 10%;
            background: url('https://i.pinimg.com/736x/7f/4b/c7/7f4bc7c9380ff12104ffaf9350ecbabb.jpg') no-repeat center center/cover;
            color: white;
            min-height: 80vh;
        }
        .hero-content {
            max-width: 50%;
            color: #333;
        }
        .hero-content h1 {
            font-size: 2.5rem;
        }
        .n {
            margin-left: 100px;
            word-spacing: 50px;
        }
        .hero-content p {
            font-size: 1.2rem;
            margin: 20px 0;
        }
        .hero-image img {
            width: 100%;
            max-width: 400px;
            border-radius: 10px;
            box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
        }
        #about {
            padding: 100px 10%;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 50px;
        }
        .im {
            margin-left: -100px;
            border: 0px;
        }
        .me {
            margin-right: -20px;
        }
        .about-content {
            display: flex;
            justify-content: space-evenly;
            align-items: center;
            text-align: center;
            padding: 10px;
            margin-inline: 100px;
        }
        .about-content img {
            width: 300px;
            border-radius: 10px;
        }
        .se {
            text-align: center;
            color: #4faaf6;
            background: #ffffff;
        }
        #services {
            display: flex;
            justify-content: space-evenly;
            align-items: center;
            text-align: center;
            padding: 0px;
        }
        .services-container {
            display: flex;
            justify-content: center;
            gap: 0px;
            margin-top: 40px;
        }
        .service {
            padding: 30px;
            width: 45%;
            display: flex;
        }
        #blog {
            padding: 100px 10%;
            text-align: center;
        }
        .blog-container {
            display: flex;
            justify-content: center;
            gap: 50px;
            margin-top: 40px;
        }
        article {
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 45%;
            text-align: left;
        }
        footer {
            display: flex;
            justify-content: space-evenly;
            align-items: center;
            padding: 30px;
            background: #ffffff;
            color: rgb(0, 0, 0);
            margin-bottom: 0px;
        }
        @media (max-width: 1024px) {
            #hero {
                flex-direction: column;
                text-align: center;
                padding: 80px 5%;
            }
            .hero-content, .hero-image {
                max-width: 100%;
            }
            .services-container, .blog-container {
                flex-direction: column;
                align-items: center;
            }
            .service, article {
                width: 80%;
                margin-bottom: 20px;
            }
            #about {
                flex-direction: column;
                text-align: center;
            }
        }
        .grid-container {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
        }
        .grid-item {
            padding: 30px;
            color: white;
            border-radius: 5px;
        }
        .blue {
            background-color: #653cf9;
        }
        .light {
            background-color: #ffffff;
            color: black;
        }
        .dark {
            background-color: #1e1e1e;
        }
        .hi a {
            color: #ffffff;
        }
        .hi a:hover {
            color: #1e1e1e;
        }
        .ih a {
            color: #007bff;
        }
        .ih a:hover {
            color: #1e1e1e;
        }
        .o a {
            color: #ffffff;
        }
        .o a:hover {
            color: #007bff;
        }
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f9f9f9;
            margin: 0;
            padding: 0;
        }
        .open-source h2 {
            color: #4169E1;
            margin-top: 40px;
            font-size: 24px;
        }
        .carousel {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }
        .card {
            background: #fff;
            padding: 20px;
            width: 250px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }
        .card.active {
            background: #1d1d1d;
            color: white;
        }
        .card .icon {
            font-size: 30px;
        }
        .card h3 {
            margin: 10px 0;
        }
        .stats {
            display: flex;
            justify-content: space-between;
            font-size: 14px;
            margin-top: 10px;
        }
        .dots {
            margin-top: 15px;
        }
        .dot {
            display: inline-block;
            width: 10px;
            height: 10px;
            background-color: #bbb;
            border-radius: 50%;
            margin: 0 5px;
        }
        .dot.active {
            background-color: #4169E1;
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <ul class="nav-links">
                <li><img src="https://i.pinimg.com/736x/40/1a/fd/401afd856234dfec61a136d54e08bb5f.jpg" width="30px"></li>
                <li><a href="#hero">Start</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#blog">Blog</a></li>
                <li><a href="#open-source">Open Source</a></li>
            </ul>
            <button class="btn-primary">Work With Me</button>
        </nav>
    </header>
    <section id="hero">
        <div class="hero-content">
            <h1>Hey, I'm Nimish</h1>
            <p>I help <u>start-ups</u>, developing outstanding web products.</p>
            <button class="btn-primary">Work With Me</button>
        </div>
        <div class="hero-image">
            <img src="https://miro.medium.com/v2/resize:fit:1400/1*1vV7ii6BwP9c5iNGt-f2MA.png" alt="Code Snippet">
        </div>
    </section>
    <div class="n">
        <a href="https://github.com/nimish-g29" target="_blank">GITHUB</a>
        <a href="https://www.linkedin.com/in/nimish-gupta-1b2211316?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app" target="_blank">LINKEDIN</a>
        <a href="https://x.com/ngbro2006?t=MvyNxkESp7r6C3RYTMyMkQ&s=09" target="_blank">TWITTER</a>
    </div>
    <section id="about">
        <div class="about-content">
            <div class="im">
                <img src="https://as2.ftcdn.net/jpg/00/32/55/37/1000_F_32553792_KYv7ZkXDVBCxhkKKky5xw4okWS3iZNyj.jpg" height="500px">
            </div>
            <div class="me">
                <h2>About Me</h2><br><br>
                <p>Passionate web developer with experience in modern web technologies. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Harum, voluptas totam sequi accusantium dignissimos, impedit dolorem quis vel cum ab, suscipit fugit dolore! Molestiae, officiis consectetur in ipsa totam fugit! Lorem ipsum dolor, sit amet consectetur adipisicing elit.<br><br>Tenetur a in, omnis aliquam esse nisi ut doloremque accusantium blanditiis repellat delectus illo velit totam eius. Provident officia alias distinctio, fugit nulla doloribus hic amet facere deleniti dicta ullam! Natus praesentium, in quae ratione exercitationem veniam molestiae veritatis autem voluptatem accusamus deleniti dignissimos amet aperiam eligendi accusantium assumenda eius maiores sint omnis est perferendis odit numquam.<br><br>Temporibus blanditiis commodi reprehenderit dolores libero sequi fugit molestias alias expedita, facere reiciendis aut voluptates odio quibusdam doloribus asperiores! Illum eum, possimus consequatur cupiditate nemo sed explicabo nisi debitis modi amet quisquam, quasi laudantium vitae.</p>
            </div>
        </div>
    </section>
    <h2 class="se">SERVICES</h2><br>
    <section id="services">
        <div>
            <img src="https://webint-image-loader.phx15.castle.fm/QXYENnb1sV9VURGsFBBQyTBrv4djZv8paGnHBjWgtps6HqgNGudcf7yY8gULedoyHhxCJcvaWfiw2X9zd1KrH8Lm3R8PDgTjbaQCP6D2VpCc93jn5ezGCG9EEHnyHv8SJmi1A8TMAbRFvRUVfcEqcBhoK" width="400px">
        </div>
        <div class="service">
            <h3>Backend Development</h3>
            <p>Providing scalable backend solutions.</p>
            <button class="btn-primary">Work With Me</button>
        </div>
    </section>
    <section id="services">
        <div class="service">
            <h3>Frontend Development</h3>
            <p>Creating visually appealing and responsive UI.</p>
            <button class="btn-primary">Work With Me</button>
        </div>
        <div>
            <img src="https://webint-image-loader.phx15.castle.fm/p1foKrFAnCGDjhiBfDhEKk1bqYUX5GtxPuvcLQUSKL8sa8wUAVxWU6MSm9EkRFU68bhy9VtiVzR8Fa5trnRV43xgkNoDTRbZAYQG1y2weTfjX8hLUfstNcvWLEvG2hABeNmdiKR9kRvpbHnQR5GVSaibo" width="400px">
        </div>
    </section>
    <section id="blog">
        <div class="grid-container">
            <div class="grid-item blue">
                <h2>Building a blog with Jekyll, Docker and GitLab</h2>
                <p>May 22, 2015 - 2 minute read</p>
                <p>Developing a Jekyll blog with Docker deployed to GitLab pages</p>
                <div class="hi"><a href="#">→ READ ARTICLE</a></div>
            </div>
            <div class="grid-item light">
                <h2>Business - A PHP library for business date calculations</h2>
                <p>May 22, 2015 - 2 minute read</p>
                <p>Discovering Business, a PHP library to ease dealing with business date calculations</p>
                <div class="ih"><a href="#">→ READ ARTICLE</a></div>
            </div>
            <div class="grid-item light">
                <h2>Data tables with Symfony, Hateoas and AngularJS</h2>
                <p>May 22, 2015 - 2 minute read</p>
                <p>Building a simple Angular table consuming a Hateoas REST API</p>
                <div class="ih"><a href="#">→ READ ARTICLE</a></div>
            </div>
            <div class="grid-item dark">
                <h2>Swap - A PHP exchange rates library</h2>
                <p>May 22, 2015 - 2 minute read</p>
                <p>Discovering Swap, an exchange rates library for PHP</p>
                <div class="o"><a href="#">→ READ ARTICLE</a></div>
            </div>
        </div>
    </section>
    <section class="open-source">
        <h2>OPEN SOURCE</h2>
        <div class="carousel">
            <div class="card">
                <h3>Swap</h3>
                <p>Currency exchange rates library for PHP.</p>
                <div class="stats">
                    <span>⭐ 645</span>
                    <span>🔗 524</span>
                </div>
            </div>
            <div class="card active">
                <h3>Swap</h3>
                <p>Currency exchange rates library for PHP.</p>
                <div class="stats">
                    <span>⭐ 645</span>
                    <span>🔗 524</span>
                </div>
            </div>
            <div class="card">
                <h3>Swap</h3>
                <p>Currency exchange rates library for PHP.</p>
                <div class="stats">
                    <span>⭐ 645</span>
                    <span>🔗 524</span>
                </div>
            </div>
        </div>
        <div class="dots">
            <span class="dot active"></span>
            <span class="dot"></span>
            <span class="dot"></span>
        </div>
    </section>
    <section class="contact">
        <div class="need"><p>Need help developing your application?</p><p>Let's get in touch!</p></div>
        <div class="wo"><button class="btn-primary">WORK WITH ME →</button></div>
    </section>
    <footer>
        <div class="fi"><img src="https://i.pinimg.com/736x/40/1a/fd/401afd856234dfec61a136d54e08bb5f.jpg" width="30px"></div>
        <p>&copy; Nimish Gupta-CSE 1ST YEAR.</p>
        <div class="social-links">
            <a href="https://github.com/nimish-g29" target="_blank">GITHUB</a>
            <a href="https://www.linkedin.com/in/nimish-gupta-1b2211316?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app" target="_blank">LINKEDIN</a>
            <a href="https://x.com/ngbro2006?t=MvyNxkESp7r6C3RYTMyMkQ&s=09" target="_blank">TWITTER</a>
        </div>
    </footer>
</body>
</html>
