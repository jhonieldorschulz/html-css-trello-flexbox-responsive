# html-css-trello-flexbox-responsive
Template responsivo baseado no Trello com HTML e CSS usando o flexbox layout

### Estrutura HTML

Vamos criar uma estrutura básica de HTML semântico:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Template Trello</title>
    <link rel="stylesheet" href="styles.css">
    <link rel="icon" type="image/x-icon" href="favicon.ico">
</head>
<body>
    <header>
        <nav class="navbar">
            <div class="logo">Trello</div>
            <ul class="nav-links">
                <li><a href="#">Início</a></li>
                <li><a href="#">Sobre</a></li>
                <li><a href="#">Contato</a></li>
            </ul>
        </nav>
    </header>
    <div class="container">
        <aside class="sidebar">
            <ul>
                <li><a href="#">Dashboard</a></li>
                <li><a href="#">Projetos</a></li>
                <li><a href="#">Tarefas</a></li>
            </ul>
        </aside>
        <main class="main-content">
            <section class="kanban-board">
                <div class="kanban-column">
                    <h2>To Do</h2>
                    <div class="kanban-item">Tarefa 1</div>
                    <div class="kanban-item">Tarefa 2</div>
                </div>
                <div class="kanban-column">
                    <h2>In Progress</h2>
                    <div class="kanban-item">Tarefa 3</div>
                </div>
                <div class="kanban-column">
                    <h2>Done</h2>
                    <div class="kanban-item">Tarefa 4</div>
                </div>
            </section>
        </main>
    </div>
</body>
</html>
```

### Estilos CSS

Agora vamos criar o arquivo CSS para estilizar o layout e torná-lo responsivo:

```css
/* styles.css */

/* Reset básico */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Estilo do corpo */
body {
    font-family: Arial, sans-serif;
    background-color: #F4F5F7;
}

/* Navbar */
.navbar {
    background-color: #026AA7;
    color: white;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
}

.navbar .logo {
    font-size: 1.5rem;
}

.navbar .nav-links {
    list-style: none;
    display: flex;
    gap: 1rem;
}

.navbar .nav-links a {
    color: white;
    text-decoration: none;
}

/* Container principal */
.container {
    display: flex;
    height: calc(100vh - 56px); /* Altura da tela menos a altura da navbar */
}

/* Sidebar */
.sidebar {
    background-color: #073B4C;
    color: white;
    width: 200px;
    padding: 1rem;
}

.sidebar ul {
    list-style: none;
}

.sidebar ul li {
    margin-bottom: 1rem;
}

.sidebar ul li a {
    color: white;
    text-decoration: none;
}

/* Main content */
.main-content {
    flex: 1;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.kanban-board {
    display: flex;
    gap: 1rem;
    overflow-x: auto;
}

.kanban-column {
    background-color: #EBECF0;
    padding: 1rem;
    border-radius: 5px;
    min-width: 250px;
    flex: 1;
}

.kanban-column h2 {
    color: #333;
    margin-bottom: 1rem;
}

.kanban-item {
    background-color: white;
    padding: 0.5rem;
    margin-bottom: 1rem;
    border-radius: 3px;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
}

/* Responsividade */
@media (max-width: 768px) {
    .navbar .nav-links {
        flex-direction: column;
        gap: 0.5rem;
    }

    .sidebar {
        display: none;
    }

    .main-content {
        padding: 0.5rem;
    }

    .kanban-board {
        flex-direction: column;
        gap: 1rem;
    }
}
```

### Explicação Detalhada

#### HTML

1. **Estrutura Básica**
   - Definimos o `DOCTYPE` para HTML5 e configuramos a codificação de caracteres para UTF-8.
   - O elemento `meta name="viewport"` é utilizado para garantir que o layout responda corretamente em dispositivos móveis.

2. **Header e Navbar**
   - Utilizamos o elemento `header` para o cabeçalho.
   - Dentro do `header`, temos uma `nav` com a classe `navbar`, que contém a logo e links de navegação.

3. **Container Principal**
   - `div` com a classe `container` que contém a barra lateral (sidebar) e o conteúdo principal (main-content).

4. **Sidebar**
   - `aside` com a classe `sidebar` que contém uma lista de links de navegação adicionais.

5. **Main Content**
   - `main` com a classe `main-content` que contém o quadro Kanban.
   - O quadro Kanban é estruturado em `section` com a classe `kanban-board` e colunas com a classe `kanban-column`.

#### CSS

1. **Reset Básico**
   - Removemos as margens e os preenchimentos padrões, e configuramos `box-sizing` para `border-box` para todos os elementos.

2. **Estilo do Corpo**
   - Definimos uma fonte padrão e uma cor de fundo para o corpo.

3. **Navbar**
   - Estilizamos a barra de navegação com uma cor de fundo, cor do texto, e utilizamos flexbox para alinhar os itens.

4. **Container Principal**
   - Utilizamos flexbox para a disposição da barra lateral e do conteúdo principal.

5. **Sidebar**
   - Definimos a largura fixa e a cor de fundo da barra lateral, além de estilizar os links.

6. **Main Content**
   - O conteúdo principal utiliza flexbox para disposição das colunas Kanban.

7. **Kanban Board**
   - As colunas Kanban são estilizadas com cores, margens, e paddings, garantindo que sejam responsivas e adaptáveis.

8. **Responsividade**
   - Ajustes para dispositivos móveis, incluindo a transformação da barra de navegação em coluna e a ocultação da barra lateral.

Esse código HTML e CSS cria um layout básico e responsivo inspirado no Trello, utilizando flexbox para garantir uma disposição flexível e adaptável a diferentes tamanhos de tela.