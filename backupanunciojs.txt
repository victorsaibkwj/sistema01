const imagens = [
            {
              url: "https://upload.wikimedia.org/wikipedia/commons/8/82/Hostinger_logo.png",
              link: "https://hostinger.com.br/?REFERRALCODE=1VICTOR444vps123",
              mensagem: "confira essa hospedagem"
            },
            {
              url: "https://upload.wikimedia.org/wikipedia/commons/f/f6/Toyota_Corolla_Limousine_Hybrid_Genf_2019_1Y7A5576.jpg",
              link: "https://uteis01.pages.dev/servicobancario",
              mensagem: "Já possui um seguro? ESTÁ TENDO ALGUMA DIFICULDADE NÓS TE AJUDAMOS"
            },
            {
              url: "https://upload.wikimedia.org/wikipedia/commons/f/f6/Toyota_Corolla_Limousine_Hybrid_Genf_2019_1Y7A5576.jpg",
              link: "https://uteis01.pages.dev/servicobancario",
              mensagem: "Já tem seguro? Se precisar de ajuda, estamos aqui!"
            },
            {
              url: "https://upload.wikimedia.org/wikipedia/commons/f/f6/Toyota_Corolla_Limousine_Hybrid_Genf_2019_1Y7A5576.jpg",
              link: "https://uteis01.pages.dev/servicobancario",
              mensagem: "Dificuldade com seu seguro? Fale com a gente agora!"
            },
            {
              url: "https://upload.wikimedia.org/wikipedia/commons/f/f6/Toyota_Corolla_Limousine_Hybrid_Genf_2019_1Y7A5576.jpg",
              link: "https://uteis01.pages.dev/servicobancario",
              mensagem: "Seguro travado? Nós resolvemos pra você — clique aqui!"
            },

            {
            url: "https://upload.wikimedia.org/wikipedia/commons/8/82/Hostinger_logo.png",
            link: "https://hostinger.com.br/?REFERRALCODE=1VICTOR444vps123",
            mensagem: "Hospede seu site com qualidade e economia!"
          },
          {
            url: "https://upload.wikimedia.org/wikipedia/commons/8/82/Hostinger_logo.png",
            link: "https://hostinger.com.br/?REFERRALCODE=1VICTOR444vps123",
            mensagem: "Hostinger: desempenho profissional para seu site"
          },
          {
            url: "https://upload.wikimedia.org/wikipedia/commons/8/82/Hostinger_logo.png",
            link: "https://hostinger.com.br/?REFERRALCODE=1VICTOR444vps123",
            mensagem: "Ganhe mais velocidade com a Hostinger"
          },
          {
            url: "https://upload.wikimedia.org/wikipedia/commons/8/82/Hostinger_logo.png",
            link: "https://hostinger.com.br/?REFERRALCODE=1VICTOR444vps123",
            mensagem: "Domine a web com a hospedagem certa"
          },
          {
            url: "https://upload.wikimedia.org/wikipedia/commons/8/82/Hostinger_logo.png",
            link: "https://hostinger.com.br/?REFERRALCODE=1VICTOR444vps123",
            mensagem: "Seu site online em minutos com a Hostinger"
          },
          {
            url: "https://upload.wikimedia.org/wikipedia/commons/8/82/Hostinger_logo.png",
            link: "https://hostinger.com.br/?REFERRALCODE=1VICTOR444vps123",
            mensagem: "Planos acessíveis e suporte incrível"
          },
          {
            url: "https://upload.wikimedia.org/wikipedia/commons/8/82/Hostinger_logo.png",
            link: "https://hostinger.com.br/?REFERRALCODE=1VICTOR444vps123",
            mensagem: "Melhore sua presença online com a Hostinger"
          },
          {
            url: "https://upload.wikimedia.org/wikipedia/commons/8/82/Hostinger_logo.png",
            link: "https://hostinger.com.br/?REFERRALCODE=1VICTOR444vps123",
            mensagem: "Confiança, desempenho e preço justo"
          },
          {
            url: "https://upload.wikimedia.org/wikipedia/commons/8/82/Hostinger_logo.png",
            link: "https://hostinger.com.br/?REFERRALCODE=1VICTOR444vps123",
            mensagem: "Tenha estabilidade e performance garantidas"
          },
          {
            url: "https://upload.wikimedia.org/wikipedia/commons/8/82/Hostinger_logo.png",
            link: "https://hostinger.com.br/?REFERRALCODE=1VICTOR444vps123",
            mensagem: "Clique e veja por que a Hostinger é top no Brasil"
          }


];


// Embaralhamento (shuffle) dos anúncios
function embaralhar(array) {
  for (let i = array.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [array[i], array[j]] = [array[j], array[i]];
  }
}

embaralhar(imagens); // <== embaralha os anúncios

let indiceAtual = 0;
const porPagina = 3;

function renderGaleria() {
  const container = document.getElementById('gallery');
  const fim = indiceAtual + porPagina;
  const itensParaMostrar = imagens.slice(indiceAtual, fim);

  itensParaMostrar.forEach(item => {
    const div = document.createElement('div');
    div.className = 'gallery-item';
    div.onclick = () => window.open(item.link, '_blank');
    div.innerHTML = `
      <img src="${item.url}" alt="${item.mensagem}">
      <div class="caption">${item.mensagem}</div>
    `;
    container.appendChild(div);
  });

  indiceAtual += porPagina;

  if (indiceAtual >= imagens.length) {
    document.getElementById('carregarMais').style.display = 'none';
  }
}

window.onload = renderGaleria;
