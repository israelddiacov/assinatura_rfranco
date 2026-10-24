# Gerador de Assinaturas Corporativas | R.Franco Engenharia

Aplicação web estática para geração de assinaturas de e-mail corporativas da **R.Franco Engenharia** com layout oficial, compatível com Microsoft Outlook (Desktop e Web), Gmail e Mozilla Thunderbird.

---

## 🔒 Proteção e Acesso Seguro (Zero-Knowledge)

Esta aplicação foi desenvolvida para rodar diretamente no **GitHub Pages** (ou qualquer hospedagem estática) mantendo a total privacidade dos dados corporativos:

- **Criptografia Militar AES-256-GCM**: Todo o código da aplicação e dados dos funcionários estão cifrados com chave derivada por **PBKDF2 (100.000 iterações com SHA-256)** no arquivo `app.enc.js`.
- **Zero Vazamento no Repositório**: Nenhuma senha, nome ou telefone de funcionário está legível no código-fonte do GitHub.
- **Descriptografia Client-Side**: O navegador descriptografa os dados em milissegundos usando a **Web Crypto API** nativa ao digitar a senha corporativa.

---

## 🚀 Como Publicar no GitHub Pages

1. Crie um repositório no seu GitHub com o nome: `assinatura_rfranco`.
2. No seu computador, abra a pasta deste projeto e execute:

```bash
git init
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/assinatura_rfranco.git
git add index.html style.css app.enc.js logo_rfranco.png README.md .gitignore
git commit -m "Gerador corporativo de assinaturas protegido"
git push -u origin main
```

3. No GitHub, acesse seu repositório `assinatura_rfranco` &rarr; **Settings** &rarr; **Pages**.
4. Em **Branch**, selecione `main` e a pasta `/ (root)`, depois clique em **Save**.
5. Em instantes o GitHub Pages fornecerá o endereço do site:
   `https://SEU_USUARIO.github.io/assinatura_rfranco/`

---

## 🔑 Como Alterar a Senha ou Atualizar Funcionários

Caso queira alterar a senha ou atualizar os dados no futuro:

1. Edite o arquivo local `src_app/app_logic.js` com os novos funcionários ou dados.
2. Execute o script Python informando a nova senha desejada:

```bash
python atualizar_senha.py "SUA_NOVA_SENHA"
```

3. Faça o commit do arquivo atualizado `app.enc.js` e envie para o GitHub:

```bash
git add app.enc.js
git commit -m "Atualizacao de dados e chave corporativa"
git push
```
