# Criar sua Carretilha

Site para personalizar a carretilha base (`carretilhaoficinadaxepa.3mf`) com dois textos curvos e desenhos nas laterais, gravados em volume negativo e espelhados, e baixar o `.3mf` pronto para o Bambu Studio.

## Acessos e limites

O login é conferido por um script do Google (Apps Script) ligado a uma planilha privada. A aba "Usuarios" guarda cada acesso com perfil, limite de carretilhas e quantas já foram usadas; as senhas ficam só como hash com sal.

- **Administrador**: usa o site normalmente e vê o botão "Administração", onde cria acessos, define o limite de carretilhas de cada um (0 = sem limite), zera a contagem, troca senhas, desbloqueia e desativa acessos.
- **Usuário**: usa o site e vê quantas carretilhas ainda pode gerar.

Antes de cada download, o site pede ao servidor para liberar a geração. Se o limite acabou, o arquivo não é baixado.

## Recursos

- **Prévia 3D**: a aba "3D" mostra a carretilha com o fundo gravado; dá para girar e aproximar.
- **Seu desenho**: o usuário envia uma imagem (PNG, JPG ou SVG) e ela é convertida em contorno para gravar nas laterais.
- **Modelos prontos**: o administrador salva combinações de texto, fonte e desenho; todos os usuários podem aplicar com um clique.
- **Minhas carretilhas**: as últimas 30 geradas por cada usuário, com miniatura. "Baixar de novo" não gasta o limite.
- **Resumo** (administrador): carretilhas do mês, por usuário, últimos 6 meses, fontes e desenhos mais usados.

## Registro

Cada geração liberada fica na aba "Registro" da planilha (usuário, textos, fonte, desenhos) com uma imagem do fundo gravado, salva numa subpasta do Drive com o nome do usuário.

## Segurança

- O conteúdo do site fica criptografado (AES-GCM). A chave só é entregue pelo servidor depois de um login válido; sem ela, o arquivo publicado só mostra a tela de login.
- Sessões expiram (12 h, ou 7 dias com "Manter conectado"). Acessos desativados perdem a entrada na hora.
- 5 senhas erradas seguidas bloqueiam o usuário por 15 minutos no servidor, além da espera crescente na tela de login.
- Política de segurança de conteúdo (CSP) restritiva: só rodam os scripts da própria página e as três bibliotecas fixadas por versão, com verificação de integridade (SRI). A página só fala com script.google.com.
- A página não abre dentro de outros sites (proteção contra clickjacking) e não é indexada por buscadores.
