<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div>
      <nav class="navbar navbar-expand-lg bg-body-tertiary">
        <div class="container-fluid">
          <a class="navbar-brand" href="#"><img class="logo" src="/src/assets/img/Captura de tela 2024-04-26 195007.png" alt=""></a>
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
              <li class="nav-item">
                <RouterLink to="/" class="nav-link active">Personagens</RouterLink>
              </li>
              <li class="nav-item">
                <RouterLink to="/about" class="nav-link">Aluno</RouterLink>
              </li>
            </ul>
            <form class="d-flex" role="search">
              <input class="form-control me-2" type="search" placeholder="Pesquisar pelo nome" aria-label="Search">
              <button class="btn btn-outline-success" type="submit">Pesquisar</button>
            </form>
          </div>
        </div>
      </nav>
        <RouterView></RouterView>
    </div>
  </header>
  <footer class="footer">
    <div class="container container-footer">
      <p>&copy; S2</p>
    </div>
  </footer>

</template>
<style>
  .logo{
    width: 5rem;
    border-radius: 8.5px;
  }
  .footer {
    background-color: #f8f9fa;
    padding: 0;
    text-align: center;
    position: fixed;
    bottom: 0;
    width: 100%;
  }

  .container-footer {
    max-width: 800px;
    margin: 0 auto;
  }
</style>