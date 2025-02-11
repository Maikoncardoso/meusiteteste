<header>
    <div class="logo-container">
        <img src="logo.png" alt="Logo" class="logo">
        <h1>Meu Site</h1>
    </div>
    <nav>
        <ul id="menu">
            <li><a href="#sobre">Sobre Mim</a></li>
            <li><a href="#portfolio">Portfólio</a></li>
            <li><a href="#">Serviços</a></li>
            <li><a href="#">Contato</a></li>
        </ul>
        <!-- Ícone do menu hambúrguer -->
        <div id="hamburger-icon" class="hamburger-icon">
            <div class="line"></div>
            <div class="line"></div>
            <div class="line"></div>
        </div>
    </nav>
</header>
/* Estilos do menu hambúrguer */
.hamburger-icon {
    display: none; /* Esconde o ícone de menu por padrão */
    cursor: pointer;
    width: 30px;
    height: 20px;
    flex-direction: column;
    justify-content: space-between;
}

.hamburger-icon .line {
    background-color: #fff;
    height: 4px;
    width: 100%;
    border-radius: 4px;
}

@media (max-width: 768px) {
    /* Esconde o menu de navegação em telas pequenas */
    nav ul {
        display: none;
        flex-direction: column;
        width: 100%;
        padding: 20px;
        background-color: #1a1a1a;
        position: absolute;
        top: 60px;
        left: 0;
    }

    /* Exibe o menu hambúrguer */
    .hamburger-icon {
        display: flex;
    }

    /* Estilo para os links do menu em dispositivos móveis */
    nav ul li {
        margin: 10px 0;
    }

    nav ul li a {
        font-size: 18px;
        color: white;
        text-decoration: none;
    }

    /* Exibe o menu quando a classe 'active' for adicionada */
    nav.active ul {
        display: flex;
    }
}
// Selecionando o ícone do menu e o menu
const hamburgerIcon = document.getElementById('hamburger-icon');
const menu = document.getElementById('menu');

// Adicionando o evento de clique no ícone
hamburgerIcon.addEventListener('click', () => {
    // Alterna a classe 'active' no elemento 'nav'
    document.querySelector('nav').classList.toggle('active');
});
<nav>
    <ul>
        <li><a href="#sobre">Sobre Mim</a></li>
        <li><a href="#portfolio">Portfólio</a></li>
        <li><a href="#">Serviços</a></li>
        <li><a href="#">Contato</a></li>
    </ul>
</nav>
// Seleciona todos os links de navegação
const links = document.querySelectorAll('nav a');

// Adiciona o evento de clique a cada link
links.forEach(link => {
    link.addEventListener('click', (e) => {
        e.preventDefault(); // Impede o comportamento padrão de navegação

        // Obtém o destino do link
        const targetId = link.getAttribute('href').slice(1);
        const targetElement = document.getElementById(targetId);

        // Rolagem suave até o destino
        targetElement.scrollIntoView({
            behavior: 'smooth',
            block: 'start'
        });
    });
});
<form id="contato-form">
    <input type="text" id="nome" placeholder="Seu nome" required>
    <input type="email" id="email" placeholder="Seu e-mail" required>
    <textarea id="mensagem" placeholder="Sua mensagem" required></textarea>
    <button type="submit">Enviar</button>
</form>
document.getElementById('contato-form').addEventListener('submit', function(e) {
    e.preventDefault(); // Impede o envio do formulário por padrão

    // Validação simples
    const nome = document.getElementById('nome').value;
    const email = document.getElementById('email').value;
    const mensagem = document.getElementById('mensagem').value;

    if (nome === "" || email === "" || mensagem === "") {
        alert("Por favor, preencha todos os campos.");
    } else {
        alert("Formulário enviado com sucesso!");
        // Aqui você pode adicionar lógica para enviar os dados via AJAX ou API
    }
});
let index = 0;
const images = document.querySelectorAll('.projeto img');
const totalImages = images.length;

function showNextImage() {
    images[index].style.display = 'none'; // Esconde a imagem atual
    index = (index + 1) % totalImages; // Incrementa o índice e reinicia ao atingir o final
    images[index].style.display = 'block'; // Exibe a próxima imagem
}

setInterval(showNextImage, 3000); // Muda a imagem a cada 3 segundos
