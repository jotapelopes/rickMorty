<style>
  .container-about {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
  }

  #title-about {
    font-size: 24px;
    margin-bottom: 10px;
  }

  p {
    font-size: 16px;
    margin-bottom: 20px;
    text-align: center;
  }

  .btn-about {
    background-color: #007bff;
    color: #fff;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    border-radius: 5px;
    cursor: pointer;
  }

  .btn-about:hover {
    background-color: #0056b3;
  }

  .about {
    background-color: #f8f9fa;
    border: 1px solid #dee2e6;
    border-radius: 5px;
    padding: 10px;
    font-size: 16px;
  }
</style>

<template>
  <div class="container container-about">
    <h1 id="title-about">Sobre o aluno</h1>
    <p>Sou o João Pedro dos Santos Lopes, tenho 19 anos. Sou aluno do curso de ADS do terceiro termo. <br> Meu RA: 1963012</p>

    <p>
      <button class="btn btn-primary btn-about" type="button" data-bs-toggle="collapse" data-bs-target="#collapseWidthExample" aria-expanded="false" aria-controls="collapseWidthExample">
        Clique aqui para saber mais sobre mim
      </button>
    </p>
    <div style="min-height: 120px;">
      <div class="collapse collapse-horizontal" id="collapseWidthExample">
        <div class="card card-body about" style="width: 300px;">
          Meus hobbys são leitura, escrita, acadêmia e corrida. <br>
          Atualmente estou estagiando com analise de requisitos, montagem de documentações e testes de qualidade de software.
        </div>
      </div>
    </div>

  </div>
</template>