<template>
  <div class="about">
    <h1 class="d-flex aling-items-flex-start mt-2 p-2">Pokedex desenvolvida por Stephanie Souza</h1>

    <p class="px-3 fs-3">Pokedex desenvolvida utilizando as ferramenta:</p>
    <ul class="mx-3 fs-4">
      <li>
        Vue.js
      </li>
      <li>
        Vite
      </li>
      <li>
        JavaScript
      </li>
      <li>
        Bootstrap
      </li>
      <li>
        Css
      </li>
      <li>
        HTML
      </li>
    </ul>
  </div>

  <hr>

  <h2 class="m-3">Sobre mim</h2>
  <p class="m-3 fs-4"> Me chamo Stephanie Souza, sou desenvolvedora Front-End em busca de crescimento profissional.
    Possuo experiência em estágios como pesquisadora e professora, além de uma trajetória sólida na área administrativa.
    Essas vivências contribuíram para o aprimoramento das minhas habilidades em trabalhar em equipe e resolução ágil de
    problemas, utilizando de forma eficiente as ferramentas disponíveis. Atualmente, estou embarcando em uma transição
    de carreira para a área da tecnologia e estudo Análise e Desenvolvimento de Sistemas. Além das atividades
    acadêmicas, estou dedicando-me ao estudo da programação Front-end, realizando cursos e projetos que podem ser
    consultados no meu LinkedIn e GitHub. Minhas principais competências englobam JavaScript, Node.js, Java, HTML, CSS,
    Python e API REST.</p>

  <hr>

  <h3 class="m-3 fs-3">Acesse minhas redes Sociais</h3>
  <a class="apresentacao__links__botao"
    href="https://www.linkedin.com/in/stephanie-souza-83a18b239?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app"><img class="img-logo"
      src="../assets/images/linkedin.svg">LinkdIn
  </a>
  <a class="apresentacao__links__botao" href="https://github.com/StephanieSouzaC"><img class="img-logo"
      src="../assets/images/github.svg">GitHub</a>
  <hr>

  <h4 class="m-3 fs-3">Minhas principais Skills:</h4>
  <div class="d-flex m-3" style="display: inline_block">
    <img align="center" alt="nodeJs" height="75" width="75"
      src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg">
    <img align="center" alt="java" height="75" width="75"
      src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg">
    <img align="center" alt="python" height="75" width="75"
      src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg">
    <img align="center" alt="html" height="75" width="75"
      src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg">
    <img align="center" alt="css" height="75" width="75"
      src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg">
    <img align="center" alt="JavaScript" height="75" width="75"
      src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-plain.svg">
  </div>

</template>

<style>
.destaque {
  font-family: 'Pokemon Solid', sans-serif;
  font-size: 2.5rem;
}

.apresentacao__links__botao {
  display: flex;
  justify-content: flex-start;
  gap: 16px;
  width: 50%;
  padding: 0.5em ;
  font-size: 1.5rem;
  font-weight: 600;
  text-align: center;
  text-decoration: none;
  color: rgb(0, 0, 0);
  margin: 1rem;
}

.img-logo{
  width: 2.5rem;
}
</style>
