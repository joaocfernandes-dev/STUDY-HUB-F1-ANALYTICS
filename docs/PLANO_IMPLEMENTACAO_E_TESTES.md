# Plano de implementação e validação — PortfolioHUB / Study Hub F1 Analytics

## 1. Objetivo

Organizar um portfólio acadêmico publicado no GitHub Pages e facilitar a consulta aos projetos e repositórios públicos do perfil GitHub. O projeto atual é um site estático em HTML, CSS e JavaScript; não é uma aplicação com backend ou autenticação de usuários.

## 2. Estado identificado na revisão dos arquivos

- `index.html` contém página responsiva com seções de apresentação, projetos, competências e contato.
- O repositório contém documentação em Markdown para perfil, disciplinas, projetos e certificados.
- O README documenta a publicação via GitHub Pages e lista tecnologias e próximos passos.
- A versão recebida não continha uma integração dinâmica com a API do GitHub.
- A versão recebida não implementava login, gestão de utilizadores, permissões por utilizador ou armazenamento de credenciais.

## 3. Melhoria implementada nesta revisão

Foi adicionada ao `index.html` uma seção que consulta a API pública do GitHub (`/users/joaocfernandes-dev/repos`) e apresenta até seis repositórios públicos ordenados pela atualização. Os elementos são criados com `textContent`, os links externos usam `rel="noopener noreferrer"`, e há uma mensagem alternativa se a consulta falhar. A integração usa apenas dados públicos e não requer token de acesso.

## 4. Limitações e segurança

- A consulta à API pública depende de conectividade e dos limites de requisição do GitHub; por isso, o site apresenta um link alternativo ao perfil.
- Como a aplicação é estática, não deve guardar segredos, tokens privados ou credenciais no código do navegador.
- Login, autorização, gestão de utilizadores e permissões reais exigiriam uma arquitetura adicional, com backend ou serviço de identidade apropriado; não devem ser declarados como implementados nesta versão.
- O acesso aos repositórios continua sujeito às permissões configuradas diretamente no GitHub.
- A alteração neste diretório local não atualiza automaticamente o site publicado: é necessário revisar, fazer commit/push para o repositório correto e confirmar o deploy do GitHub Pages.

## 5. Plano de testes

1. Abrir `index.html` localmente e confirmar que a página carrega sem erros visuais.
2. Verificar navegação entre Sobre, Projetos, GitHub, Competências e Contato.
3. Com internet disponível, confirmar que a seção GitHub apresenta repositórios e links válidos.
4. Simular indisponibilidade de rede ou falha da API e confirmar que aparece a mensagem alternativa e o link do perfil.
5. Testar em largura desktop e celular, verificando que os cartões se reorganizam.
6. Abrir os links externos e confirmar que levam aos destinos esperados.
7. Após publicar a atualização, repetir os testes no endereço do GitHub Pages.

## 6. Evidências a guardar para a entrega

- Captura da página inicial publicada.
- Captura da seção de repositórios carregados do GitHub.
- Captura do repositório com o commit da alteração.
- Captura do site publicado após o deploy.
- Registo das interações reais com o Google Gemini, se utilizado durante a etapa de revisão, incluindo recomendações aproveitadas e alterações efetivamente feitas.

## 7. Uso de IA e transparência

A documentação final deve indicar com precisão quais ferramentas de IA foram utilizadas, em que etapa e para qual finalidade. Não declarar o Gemini como ferramenta utilizada em etapas anteriores se isso não ocorreu. Se o Gemini for utilizado na revisão atual, guardar o prompt e a resposta real e explicar quais sugestões foram avaliadas, adotadas ou rejeitadas.
