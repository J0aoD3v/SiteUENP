<template>
  <div id="app">
    <header>
      <img
        src="https://uenp.edu.br/images/institucional/logo/uenp-logoportal.png"
        alt="Logo UENP"
        class="logo"
      />
      <nav>
        <ul>
          <li>
            <a href="#welcome-list">
              <img
                src="https://github.com/J0aoD3v/j0aod3v.github.io/blob/main/icon23.jpg?raw=true"
                alt="Lista de Boas-Vindas 2024"
                class="nav-icon"
              />
            </a>
          </li>
          <li>
            <a
              href="https://uenp.edu.br/doc-conselhos-uenp/cepe/cepe-resolucoes/cepe-resolucoes-2019/13998-resolucao-033-2019-cepe-uenp/file"
            >
              <img
                src="https://uenp.edu.br/images/eventos/2023/welcome/icones/btn1-sem-trote.png"
                alt="Trote é Proibido"
                class="nav-icon"
              />
            </a>
          </li>
          <li>
            <a href="https://uenp.edu.br/ouvidoria">
              <img
                src="https://uenp.edu.br/images/eventos/2023/welcome/icones/btn1-denuncie.png"
                alt="Denuncie"
                class="nav-icon"
              />
            </a>
          </li>
          <li>
            <a href="https://uenp.edu.br/sobre-graduacao/normas-academicas">
              <img
                src="https://uenp.edu.br/images/eventos/2023/welcome/icones/btn1-guia-estudante.png"
                alt="Guia do Estudante"
                class="nav-icon"
              />
            </a>
          </li>
          <li>
            <a href="https://uenp.edu.br/sobre-graduacao/calendario-academico">
              <img
                src="https://uenp.edu.br/images/eventos/2023/welcome/icones/btn1-calendario.png"
                alt="Calendário Acadêmico"
                class="nav-icon"
              />
            </a>
          </li>
        </ul>
      </nav>
    </header>
    <main>
      <h1>{{ message }}</h1>
      <p>
        Este é um site para divulgar nossa recepção aos calouros. Sempre ficamos
        muito animados em receber novos alunos em nossa instituição e por isso
        queremos mais formas de divulgar nossa faculdade e os cursos que
        oferecemos nela. 😊
      </p>
      <section id="student-welcome">
        <h2>Acolhimento ao Estudante ❤</h2>
        <div class="button-container">
          <p>
            <button @click="goToPage1('https://uenp.edu.br/prograd')">
              Conheça a Pró-Reitoria de Graduação - PROGRAD 🎓
            </button>
          </p>
          <p>
            <button @click="goToPage2('https://uenp.edu.br/nae')">
              Conheça o Núcleo de Apoio e Assistência Estudantil - NAE ✨
            </button>
          </p>
          <p>
            <button @click="goToPage3('https://uenp.edu.br/apsi')">
              Conheça o Apoio Psicológico - APSI 🧠
            </button>
          </p>
          <p>
            <button @click="goToPage4('https://uenp.edu.br/moradia-estudantil')">
              Conheça a Moradia Estudantil 🏠
            </button>
          </p>
        </div>
      </section>
      <section id="campus-gallery">
        <h2>Galeria de Imagens dos Nossos Campi 🖼</h2>
        <div class="carousel-container">
          <p>
            <button @click="prevImage">◀</button>
          </p>
          <img
            :src="images[currentImage].url"
            alt="Imagem do Campus"
            class="campus-image"
          />
          <p>{{ images[currentImage].caption }}</p>
          <button @click="nextImage">▶</button>
          <p></p>
          <footer>
            <h2>Siga as nossas redes sociais da UENP 🌐</h2>
            <ul>
              <li>
                <a
                  href="https://www.facebook.com/UENP.Oficial/"
                  target="_blank"
                >
                  <img
                    src="https://uenp.edu.br/images/eventos/2020/covid19/logo_facebook.png"
                    alt="Facebook"
                  />
                </a>
              </li>
              <li>
                <a
                  href="https://www.instagram.com/uenp_oficial/"
                  target="_blank"
                >
                  <img
                    src="https://uenp.edu.br/images/eventos/2020/covid19/logo_instagram.png"
                    alt="Instagram"
                  />
                </a>
              </li>
            </ul>
            <p>
              Desenvolvido por
              <a href="https://github.com/J0aoD3v" target="_blank">J0aoD3v</a>
              👨‍💻
            </p>
          </footer>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "Bem vindo a UENP 🏫",
      images: [
        {
          url:
            "https://uenp.edu.br/media/k2/items/cache/c44b3abd57ccfbc620ba9eaafbc28bd6_XL.jpg",
          caption: "Campus Jacarezinho (Reitoria)"
        },
        {
          url:
            "https://upload.wikimedia.org/wikipedia/commons/2/25/UENP_-_Universidade_Estadual_do_Norte_do_Paran%C3%A1_-_Campus_Luiz_Meneghel.JPG",
          caption: "Campus Luiz Meneghel (Entrada)"
        },
        {
          url:
            "https://uenp.edu.br/media/k2/items/cache/f0d4788c7ddb1dcb4a7179106aa13453_XL.jpg",
          caption: "Campus Cornélio Procópio (Entrada)"
        }
      ],
      currentImage: 0
    };
  },
  methods: {
    goToPage(url) {
      window.location.href = url;
    },
    nextImage() {
      this.currentImage = (this.currentImage + 1) % this.images.length;
    },
    prevImage() {
      this.currentImage =
        (this.currentImage - 1 + this.images.length) % this.images.length;
    }
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Rubik&display=swap");
#app {
  font-family: "Rubik", sans-serif;
  color: #ffffff;
  background-color: #0183d1;
}

header {
  background-color: #008fed;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
}

.logo {
  height: 50px;
}

nav ul {
  list-style: none;
  display: flex;
}

.nav-icon {
  width: auto;
  height: 50px;
}

nav a {
  color: #ffffff;
  text-decoration: none;
  margin-left: 2rem;
}

main {
  padding: 2rem;
}

#student-welcome {
  background-color: #01568d;
  padding: 2rem;
  margin-top: 2rem;
}

.button-container button {
  background-color: #008fed;
  color: #ffffff;
  border: none;
  border-radius: 2em;
  padding: 0.75em 2em;
  margin-right: 1rem;
  cursor: pointer;
}

.button-container button:hover {
  background-color: #013a62;
}

.carousel-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.campus-image {
  width: 100%;
  height: auto;
}

footer {
  background-color: #008fed;
  color: #ffffff;
  padding: 2rem;
  text-align: center;
}

footer a {
  color: #ffffff;
  text-decoration: none;
}

footer ul {
  list-style: none;
  display: flex;
  justify-content: center;
  gap: 1rem;
}

footer img {
  width: 24px;
  height: 24px;
}
</style>
