<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#101827">
<meta name="description" content="RecuperaOrçamentos: organize propostas, acompanhe clientes e tenha mais controle sobre suas vendas.">
<title>RecuperaOrçamentos | Venda mais</title>
<style>
:root {
  --bg:#f4f7fb; --card:#fff; --ink:#172338;
  --muted:#718096; --primary:#315efb; --line:#e5eaf2;
  --green:#13865b; --red:#c94040; --nav:#101827;
}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--ink);
font-family:system-ui,-apple-system,Arial,sans-serif}
button,input,select,textarea{font:inherit}
button{cursor:pointer}
.topbar{background:var(--nav);color:white;padding:20px 16px}
.topinner{max-width:1100px;margin:auto;display:flex;
align-items:center;justify-content:space-between;gap:12px}
.brand{font-size:19px;font-weight:850;letter-spacing:-.5px}
.brand span{color:#80a0ff}
.tagline{font-size:12px;color:#b9c6d8;margin-top:4px}
.container{max-width:1100px;margin:auto;padding:20px 15px 50px}
.hero{background:linear-gradient(130deg,#182a52,#315efb);
color:white;padding:25px;border-radius:19px;margin-bottom:20px}
.hero h1{font-size:clamp(24px,5vw,36px);margin:0 0 10px}
.hero p{line-height:1.6;color:#e0e8ff;max-width:650px}
.btn{border:0;border-radius:10px;padding:11px 15px;
font-weight:750;display:inline-flex;align-items:center;
justify-content:center;text-decoration:none;gap:6px}
.primary{background:var(--primary);color:white}
.white{background:white;color:#2446bf}
.dark{background:var(--nav);color:white}
.outline{background:white;border:1px solid var(--line);color:var(--ink)}
.danger{background:#fff0f0;color:var(--red)}
.small{padding:7px 10px;font-size:12px}
.full{width:100%}
.grid{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:13px}
.card{background:var(--card);border:1px solid var(--line);
border-radius:15px;padding:17px;min-width:0}
.metric-label{font-size:12px;color:var(--muted)}
.metric-value{font-size:25px;font-weight:850;margin-top:8px;
overflow-wrap:anywhere}
.metric-note{font-size:11px;color:var(--muted);margin-top:5px}
.section{margin-top:25px}
.sectionhead{display:flex;align-items:center;justify-content:space-between;
gap:12px;flex-wrap:wrap;margin-bottom:13px}
h2{font-size:20px;margin:0}
h3{font-size:16px;margin:0 0 12px}
.muted{color:var(--muted);font-size:13px;line-height:1.6}
.row{display:flex;gap:9px;align-items:center;flex-wrap:wrap}
.field{display:flex;flex-direction:column;gap:6px;margin-bottom:13px;
flex:1;min-width:0}
label{font-size:12px;font-weight:750;color:#45546b}
input,select,textarea{width:100%;padding:11px 12px;
border:1px solid #dce3ee;border-radius:9px;background:white;color:var(--ink)}
textarea{resize:vertical;min-height:75px}
input:focus,select:focus,textarea:focus{outline:2px solid #a8bbff;
border-color:var(--primary)}
.formgrid{display:grid;grid-template-columns:1fr 1fr;gap:0 12px}
.wide{grid-column:1/-1}
.tablewrap{overflow-x:auto}
table{border-collapse:collapse;width:100%;font-size:13px}
th,td{text-align:left;padding:12px 9px;border-bottom:1px solid var(--line);
vertical-align:top}
th{font-size:11px;color:var(--muted);text-transform:uppercase}
td{overflow-wrap:anywhere}
.badge{display:inline-block;padding:5px 8px;border-radius:20px;
font-size:11px;font-weight:800;background:#edf1f8;color:#45546b}
.badge.pending{background:#fff4d9;color:#885e00}
.badge.won{background:#def8eb;color:#087447}
.badge.lost{background:#ffe6e6;color:#ad3030}
.plans{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:14px}
.plan{display:flex;flex-direction:column;gap:12px}
.plan.featured{border:2px solid var(--primary)}
.price{font-size:29px;font-weight:900;letter-spacing:-1px}
.price small{font-size:12px;font-weight:500;color:var(--muted);
letter-spacing:0}
.plan ul{padding-left:19px;line-height:1.9;font-size:13px;flex:1}
.popular{color:var(--primary);font-size:11px;font-weight:900}
.notice{background:#eef3ff;border:1px solid #d7e2ff;color:#344b87;
padding:13px;border-radius:10px;font-size:12px;line-height:1.6}
.empty{text-align:center;padding:28px;color:var(--muted);font-size:13px}
.toolbar{display:grid;grid-template-columns:1fr 190px;gap:10px;margin-bottom:12px}
.footer{text-align:center;color:var(--muted);font-size:12px;padding:25px 10px}
hr{border:0;border-top:1px solid var(--line);margin:20px 0}
.hidden{display:none!important}
@media(max-width:760px){
 .grid{grid-template-columns:repeat(2,minmax(0,1fr))}
 .plans{grid-template-columns:1fr}
 .topbar{padding:16px 13px}
 .container{padding:14px 11px 35px}
 .hero{padding:20px}
 .formgrid{grid-template-columns:1fr}
 .wide{grid-column:auto}
 .toolbar{grid-template-columns:1fr}
 .metric-value{font-size:22px}
 .sectionhead .btn{flex:1}
}
</style>
</head>
<body>
<header class="topbar">
  <div class="topinner">
    <div>
      <div class="brand">Recupera<span>Orçamentos</span></div>
      <div class="tagline">Organize propostas. Acompanhe clientes. Venda melhor.</div>
    </div>
    <a class="btn white small" href="#planos">Ver planos</a>
  </div>
</header>

<main class="container">
  <section class="hero">
    <h1>Não deixe seus orçamentos esquecidos.</h1>
    <p>Organize seus clientes, acompanhe propostas pendentes e saiba quais oportunidades precisam de atenção. Tudo em um painel simples.</p>
    <div class="row">
      <button class="btn white" onclick="novoOrcamento()">+ Cadastrar orçamento</button>
      <a class="btn" style="background:#243c79;color:white" href="#painel">Abrir painel ↓</a>
    </div>
  </section>

  <section id="painel">
    <div class="sectionhead">
      <div>
        <h2>Visão geral</h2>
        <div class="muted">Resumo dos registros deste navegador.</div>
      </div>
      <button class="btn outline" onclick="exportarDados()">Exportar backup</button>
    </div>
    <div class="grid">
      <div class="card">
        <div class="metric-label">Orçamentos cadastrados</div>
        <div class="metric-value" id="mTotal">0</div>
        <div class="metric-note">Todos os registros</div>
      </div>
      <div class="card">
        <div class="metric-label">Pendentes</div>
        <div class="metric-value" id="mPendentes">0</div>
        <div class="metric-note">Precisam de acompanhamento</div>
      </div>
      <div class="card">
        <div class="metric-label">Recuperados</div>
        <div class="metric-value" id="mRecuperados">0</div>
        <div class="metric-note">Marcados como vendidos</div>
      </div>
      <div class="card">
        <div class="metric-label">Valor recuperado</div>
        <div class="metric-value" id="mValor">R$ 0</div>
        <div class="metric-note">Soma dos valores marcados como recuperados</div>
      </div>
    </div>
  </section>

  <section class="section" id="cadastro">
    <div class="sectionhead">
      <div>
        <h2 id="formTitulo">Cadastrar orçamento</h2>
        <div class="muted">Preencha os dados para acompanhar cada oportunidade.</div>
      </div>
    </div>
    <div class="card">
      <form id="formOrcamento">
        <input type="hidden" id="editId">
        <div class="formgrid">
          <div class="field">
            <label for="cliente">Nome do cliente *</label>
            <input id="cliente" required maxlength="100" placeholder="Ex.: João Silva">
          </div>
          <div class="field">
            <label for="telefone">WhatsApp (com DDD)</label>
            <input id="telefone" inputmode="tel" placeholder="Ex.: 41999999999" maxlength="25">
          </div>
          <div class="field">
            <label for="servico">Produto ou serviço *</label>
            <input id="servico" required maxlength="150" placeholder="Ex.: Instalação de ar-condicionado">
          </div>
          <div class="field">
            <label for="valor">Valor do orçamento (R$) *</label>
            <input id="valor" type="number" min="0" max="999999999" step="0.01" required placeholder="250.00">
          </div>
          <div class="field">
            <label for="status">Situação</label>
            <select id="status">
              <option value="pendente">Pendente</option>
              <option value="won">Recuperado / vendido</option>
              <option value="lost">Perdido</option>
            </select>
          </div>
          <div class="field">
            <label for="retorno">Data do próximo contato</label>
            <input id="retorno" type="date">
          </div>
          <div class="field wide">
            <label for="observacoes">Observações</label>
            <textarea id="observacoes" maxlength="1000" placeholder="Ex.: Cliente pediu para retornar na sexta-feira."></textarea>
          </div>
        </div>
        <div class="row">
          <button class="btn primary" type="submit" id="salvarBtn">Salvar orçamento</button>
          <button class="btn outline hidden" type="button" id="cancelarBtn" onclick="cancelarEdicao()">Cancelar edição</button>
        </div>
      </form>
    </div>
  </section>

  <section class="section" id="clientes">
    <div class="sectionhead">
      <div>
        <h2>Meus orçamentos</h2>
        <div class="muted">Edite, acompanhe ou prepare uma mensagem para o cliente.</div>
      </div>
    </div>
    <div class="toolbar">
      <input id="busca" placeholder="Buscar cliente ou serviço..." aria-label="Buscar orçamento">
      <select id="filtro" aria-label="Filtrar situação">
        <option value="todos">Todas as situações</option>
        <option value="pendente">Pendentes</option>
        <option value="won">Recuperados</option>
        <option value="lost">Perdidos</option>
      </select>
    </div>
    <div class="card">
      <div class="tablewrap">
        <table>
          <thead><tr>
            <th>Cliente / serviço</th><th>Valor</th><th>Situação</th><th>Retorno</th><th>Ações</th>
          </tr></thead>
          <tbody id="lista"></tbody>
        </table>
      </div>
      <div id="vazio" class="empty">Nenhum orçamento cadastrado. Comece adicionando seu primeiro cliente.</div>
    </div>
  </section>

  <section class="section" id="planos">
    <div class="sectionhead">
      <div>
        <h2>Escolha seu plano</h2>
        <div class="muted">Comece a organizar melhor suas oportunidades de venda.</div>
      </div>
    </div>
    <div class="plans">
      <article class="card plan">
        <div><h3>Plano Básico</h3><div class="muted">Para começar a se organizar.</div></div>
        <div class="price">R$ 19,90 <small>/ mês</small></div>
        <ul>
          <li>Controle de orçamentos</li>
          <li>Cadastro de clientes</li>
          <li>Acompanhamento de situações</li>
          <li>Mensagens de retorno</li>
        </ul>
        <a class="btn primary full" href="https://mpago.la/1gzHZgi" target="_blank" rel="noopener noreferrer">Assinar Básico</a>
      </article>
      <article class="card plan featured">
        <div class="popular">PLANO EM DESTAQUE</div>
        <div><h3>Plano Intermediário</h3><div class="muted">Para quem acompanha mais oportunidades.</div></div>
        <div class="price">R$ 39,90 <small>/ mês</small></div>
        <ul>
          <li>Recursos do plano Básico</li>
          <li>Organização da carteira de clientes</li>
          <li>Indicadores de acompanhamento</li>
          <li>Exportação de backup</li>
        </ul>
        <a class="btn primary full" href="https://mpago.la/2nAe1ew" target="_blank" rel="noopener noreferrer">Assinar Intermediário</a>
      </article>
      <article class="card plan">
        <div><h3>Plano Pro</h3><div class="muted">Para quem busca mais controle.</div></div>
        <div class="price">R$ 59,90 <small>/ mês</small></div>
        <ul>
          <li>Recursos de organização disponíveis</li>
          <li>Gestão de propostas</li>
          <li>Indicadores de vendas recuperadas</li>
          <li>Backup dos dados</li>
        </ul>
        <a class="btn primary full" href="https://mpago.la/2eVmn4i" target="_blank" rel="noopener noreferrer">Assinar Pro</a>
      </article>
    </div>
  </section>

  <section class="section">
    <div class="card">
      <h3>Seus dados e sua privacidade</h3>
      <p class="muted">Os registros desta demonstração ficam no armazenamento local deste navegador. Eles não são sincronizados entre dispositivos e podem ser perdidos se os dados do navegador forem apagados. Use a opção de backup para exportar seus registros.</p>
      <div class="row">
        <button class="btn outline" onclick="exportarDados()">Baixar backup JSON</button>
        <button class="btn danger" onclick="limparDados()">Apagar todos os registros</button>
      </div>
    </div>
  </section>
</main>

<footer class="footer">
  RecuperaOrçamentos · Ferramenta de organização comercial.<br>
  Resultados dependem do uso da ferramenta e do relacionamento com os clientes.
</footer>

<script>
"use strict";

const STORAGE_KEY = "recupera_orcamentos_v1";
let registros = carregar();

function carregar() {
  try {
    const dados = JSON.parse(localStorage.getItem(STORAGE_KEY) || "[]");
    return Array.isArray(dados) ? dados : [];
  } catch {
    return [];
  }
}

function salvar() {
  try {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(registros));
    return true;
  } catch (erro) {
    alert("Não foi possível salvar. Verifique o armazenamento do navegador e exporte um backup.");
    return false;
  }
}

function moeda(valor) {
  return Number(valor || 0).toLocaleString("pt-BR", {
    style: "currency", currency: "BRL"
  });
}

function textoSeguro(valor) {
  return String(valor ?? "").replace(/[&<>"']/g, c => ({
    "&":"&amp;", "<":"&lt;", ">":"&gt;",
    '"':"&quot;", "'":"&#39;"
  })[c]);
}

function dataBR(data) {
  if (!data) return "Não definida";
  const partes = data.split("-");
  return partes.length === 3 ? `${partes[2]}/${partes[1]}/${partes[0]}` : data;
}

function classeStatus(status) {
  if (status === "won") return "won";
  if (status === "lost") return "lost";
  return "pending";
}

function nomeStatus(status) {
  if (status === "won") return "Recuperado";
  if (status === "lost") return "Perdido";
  return "Pendente";
}

function atualizarPainel() {
  document.getElementById("mTotal").textContent = registros.length;
  document.getElementById("mPendentes").textContent =
    registros.filter(r => r.status === "pendente").length;
  document.getElementById("mRecuperados").textContent =
    registros.filter(r => r.status === "won").length;
  document.getElementById("mValor").textContent = moeda(
    registros.filter(r => r.status === "won")
      .reduce((soma, r) => soma + Number(r.valor || 0), 0)
  );
}

function renderizar() {
  atualizarPainel();
  const busca = document.getElementById("busca").value.trim().toLowerCase();
  const filtro = document.getElementById("filtro").value;

  const filtrados = registros.filter(r => {
    const corresponde =
      `${r.cliente} ${r.servico} ${r.telefone || ""}`.toLowerCase().includes(busca);
    return corresponde && (filtro === "todos" || r.status === filtro);
  });

  const lista = document.getElementById("lista");
  document.getElementById("vazio").classList.toggle("hidden", filtrados.length > 0);
  lista.innerHTML = filtrados.map(r => `
    <tr>
      <td><strong>${textoSeguro(r.cliente)}</strong><br>
        <span class="muted">${textoSeguro(r.servico)}</span>
        ${r.observacoes ? `<br><span class="muted">${textoSeguro(r.observacoes)}</span>` : ""}
      </td>
      <td>${moeda(r.valor)}</td>
      <td><span class="badge ${classeStatus(r.status)}">${nomeStatus(r.status)}</span></td>
      <td>${dataBR(r.retorno)}</td>
      <td>
        <div class="row" style="min-width:150px">
          <button class="btn outline small" onclick="editar('${r.id}')">Editar</button>
          <button class="btn outline small" onclick="mensagem('${r.id}')">WhatsApp</button>
          <button class="btn danger small" onclick="excluir('${r.id}')">Excluir</button>
        </div>
      </td>
    </tr>
  `).join("");
}

function novoOrcamento() {
  cancelarEdicao();
  document.getElementById("cliente").focus();
  document.getElementById("cadastro").scrollIntoView({behavior:"smooth"});
}

document.getElementById("formOrcamento").addEventListener("submit", function(e) {
  e.preventDefault();

  const idAtual = document.getElementById("editId").value;
  const dados = {
    id: idAtual || (Date.now().toString(36) + Math.random().toString(36).slice(2,8)),
    cliente: document.getElementById("cliente").value.trim(),
    telefone: document.getElementById("telefone").value.trim(),
    servico: document.getElementById("servico").value.trim(),
    valor: Number(document.getElementById("valor").value),
    status: document.getElementById("status").value,
    retorno: document.getElementById("retorno").value,
    observacoes: document.getElementById("observacoes").value.trim()
  };

  if (!dados.cliente || !dados.servico || !Number.isFinite(dados.valor) || dados.valor < 0) {
    alert("Confira o nome do cliente, o serviço e o valor.");
    return;
  }

  const anterior = registros;
  if (idAtual) {
    registros = registros.map(r => r.id === idAtual ? dados : r);
  } else {
    registros.unshift(dados);
  }

  if (!salvar()) {
    registros = anterior;
    return;
  }

  cancelarEdicao();
  renderizar();
  alert(idAtual ? "Orçamento atualizado!" : "Orçamento cadastrado!");
  document.getElementById("clientes").scrollIntoView({behavior:"smooth"});
});

function editar(id) {
  const r = registros.find(x => x.id === id);
  if (!r) return;

  document.getElementById("editId").value = r.id;
  document.getElementById("cliente").value = r.cliente;
  document.getElementById("telefone").value = r.telefone || "";
  document.getElementById("servico").value = r.servico;
  document.getElementById("valor").value = r.valor;
  document.getElementById("status").value = r.status;
  document.getElementById("retorno").value = r.retorno || "";
  document.getElementById("observacoes").value = r.observacoes || "";
  document.getElementById("formTitulo").textContent = "Editar orçamento";
  document.getElementById("salvarBtn").textContent = "Salvar alterações";
  document.getElementById("cancelarBtn").classList.remove("hidden");
  document.getElementById("cadastro").scrollIntoView({behavior:"smooth"});
}

function cancelarEdicao() {
  document.getElementById("formOrcamento").reset();
  document.getElementById("editId").value = "";
  document.getElementById("formTitulo").textContent = "Cadastrar orçamento";
  document.getElementById("salvarBtn").textContent = "Salvar orçamento";
  document.getElementById("cancelarBtn").classList.add("hidden");
}

function excluir(id) {
  if (!confirm("Deseja realmente excluir este orçamento?")) return;
  const anterior = registros;
  registros = registros.filter(r => r.id !== id);
  if (!salvar()) {
    registros = anterior;
    return;
  }
  renderizar();
}

function copiarTexto(texto) {
  navigator.clipboard.writeText(texto).then(() => {
    alert("Mensagem copiada para a área de transferência!");
  }).catch(() => {
    alert("Não foi possível copiar automaticamente.");
  });
}

function mensagem(id) {
  const r = registros.find(x => x.id === id);
  if (!r) return;

  const msg = `Olá, ${r.cliente}! Tudo bem? Estou entrando em contato para saber se você teve a oportunidade de avaliar o orçamento de ${r.servico}, no valor de ${moeda(r.valor)}. Posso esclarecer alguma dúvida ou ajudar no que precisar?`;
  
  if (!r.telefone) {
    if (confirm("Este cliente não tem telefone cadastrado. Deseja copiar a mensagem para enviar manualmente?")) {
      copiarTexto(msg);
    }
    return;
  }

  let numero = r.telefone.replace(/\D/g, "");
  if (numero.length >= 10 && numero.length <= 11) numero = "55" + numero;
  
  const url = `https://wa.me/${numero}?text=${encodeURIComponent(msg)}`;
  window.open(url, "_blank");
}

function exportarDados() {
  const dadosStr = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(registros, null, 2));
  const downloadAnchor = document.createElement('a');
  downloadAnchor.setAttribute("href", dadosStr);
  downloadAnchor.setAttribute("download", "backup_recupera_orcamentos.json");
  document.body.appendChild(downloadAnchor);
  downloadAnchor.click();
  downloadAnchor.remove();
}

function limparDados() {
  if (confirm("Tem certeza que deseja apagar TODOS os registros? Esta ação não pode ser desfeita.")) {
    registros = [];
    salvar();
    renderizar();
    alert("Todos os registros foram apagados.");
  }
}

document.getElementById("busca").addEventListener("input", renderizar);
document.getElementById("filtro").addEventListener("change", renderizar);

renderizar();
</script>
</body>
</html>