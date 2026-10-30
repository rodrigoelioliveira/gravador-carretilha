# Gravador de Carretilha

Site para personalizar a carretilha base (`carretilhaoficinadaxepa.3mf`) com dois textos curvos e desenhos nas laterais, gravados em volume negativo e espelhados, e baixar o `.3mf` pronto para o Bambu Studio.

## Segurança

- O conteúdo do site fica criptografado (AES-GCM com chave derivada do usuário e da senha por PBKDF2-SHA256, 1.000.000 de iterações). Sem a senha, o arquivo publicado só mostra a tela de login.
- Política de segurança de conteúdo (CSP) restritiva: só rodam os scripts da própria página e as três bibliotecas fixadas por versão, com verificação de integridade (SRI). A página não envia dados para nenhum servidor.
- A página não abre dentro de outros sites (proteção contra clickjacking) e não é indexada por buscadores.
- Tentativas erradas seguidas geram espera crescente na tela de login.
