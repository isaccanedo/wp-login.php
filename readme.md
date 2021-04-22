# Renomear wp-login.php   

# 1. Descrição

Renomear wp-login.php é um plugin muito leve que permite que você altere wp-login.php com facilidade e segurança para qualquer coisa que você quiser. Ele literalmente não renomeia ou altera arquivos no núcleo, nem adiciona regras de reescrita. Ele simplesmente intercepta solicitações de página e funciona em qualquer site WordPress. O diretório wp-admin e a página wp-login.php tornam-se inacessíveis, então você deve marcar ou lembrar o url. Desativar este plugin traz seu site de volta exatamente ao estado em que estava antes.

# 2. Compatibilidade

Todas as coisas relacionadas ao login, como formulário de registro, formulário de senha perdida, widget de login e sessões expiradas, continuam funcionando.

Também é compatível com qualquer plugin que se conecte ao formulário de login, incluindo

- uddyPress;
- bbPress;
- Limite as tentativas de login;
- e troca de usuário.

Obviamente, isso não funciona com plug-ins * codificados * em wp-login.php.

Funciona com vários locais, mas não foi testado com subdomínios. Ativá-lo para uma rede permite definir um padrão para toda a rede. Sites individuais ainda podem renomear sua página de login para outra coisa.

Se estiver usando um ** plug-in de cache de página **, você deve adicionar o slug do novo url de login à lista de páginas que não devem ser armazenadas em cache.

Se desejar, você pode bloquear wp-login.php com ```.htaccess``` a partir de agora.

# 3. Instalação

1. Vá para Plugins ›Adicionar Novo.
2. Pesquise * Rename wp-login.php *.
3. Procure este plugin, baixe e ative-o.
4. A página o redirecionará para as configurações. Renomeie wp-login.php aqui.
5. Você pode alterar esta opção a qualquer momento, basta voltar para Configurações ›Links permanentes› Renomear wp-login.php.

# 4. Perguntas frequentes

### Esqueci meu URL de login!

Vá para seu banco de dados MySQL e procure o valor de ```rwl_page``` na tabela de opções, ou remova a pasta ```rename-wp-login``` de sua pasta ```plugins```, faça o login através de wp-login.php e reinstale o plugin .

Em uma instalação multisite, a opção ```rwl_page``` estará na tabela sitemeta, se não houver tal opção na tabela de opções.

## Changelog

### 2.5.5

* Adicione ```load_plugin_textdomain``` ausente.

### 2.5.4

* Adicionado suporte i18n.

### 2.5

* Use wp-login.php em vez de copiar o arquivo.
* Não adicione avisos para W3 Total Cache e WP Super Cache.

### 2.4

* Compatível com WordPress 4.0.

### 2.3

* Compatível com WordPress 3.9.
* Corrigir o problema em que o slug volta ao padrão ao salvar a estrutura do permalink.

### 2.2.4

* Problemas de SSL corrigidos.
* Defina REQUEST_URI de volta.
* Verifique se as funções wp-login.php existem para evitar futuros erros fatais.

### 2.2.3

* Filtros de URL fixos.

### 2.2

* Corrigido o problema em que as solicitações redirecionam para a nova página de login.
* Barra final com base na estrutura do permalink.

### 2.1

* Funciona agora com permalinks não bonitos!
* Dá uma mensagem ao usar W3 Total Cache ou WP Super Cache para atualizar as opções.

### 2.0.1

* Impede redirecionamentos bonitos como / login e / admin.
* Simplifica alguns códigos.
* Força a página de login com uma barra final.
* Substitui um wp_redirect por wp_safe_redirect.
* Mostra mensagem de erro no administrador da rede se permalinks não estiverem habilitados para o site principal.

### 2.0

* Este plugin agora pode ser ativado para uma rede e um padrão para toda a rede pode ser definido.
* O plugin agora se conecta após o init para garantir que quaisquer personalizações no formulário de login sejam conectadas antes dele.
* Os links agora devem ser corrigidos quando o SSL está ativado.

### 1.9

* wp-admin agora terá uma mensagem `wp_die ()` em vez de um modelo 404 porque isso causou problemas.
* A versão mínima agora é 3.8.
* Adicionadas atualizações de wp-login.php no 3.8.

### 1.8

* OOP PHP.
* Requer WordPress 3.7 ou superior.
* Compatível com MultiViews.

### 1.7

* Tornado compatível com WordPress 3.7.

### 1.6

* Corrigido o link de login quando `site_url ()` ≠ `home_url ()`.
* Adicionado um [espelho] (https://github.com/ellatrix/rename-wp-login) no GitHub.

### 1.5

* Tornou [User Switching] (http://wordpress.org/plugins/user-switching/) compatível.

### 1.4

* Carregamento de página mais rápido.
* Corrigido erro 404 para estruturas de permalink com um caminho prefixado. Permalinks “quase bonitos” também funcionam agora.
* Limpeza de código.

### 1.3

* Evita que o plugin funcione quando não houver estrutura de permalink.

### 1.2

* Corrigido o código de status da página de login personalizada.

### 1.1

* Acesso bloqueado ao wp-admin para evitar um redirecionamento para a nova página de login.

### 1.0

* Versão inicial.