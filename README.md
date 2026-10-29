# Rally App (Testing Jetpack Compose)

Este repositório contém a implementação dos testes instrumentados de interface (UI) desenvolvidos para o aplicativo **Rally**, como parte do curso oficial do Google de Android Basics com Jetpack Compose.

O foco principal deste projeto é aprender e aplicar estratégias de testes automatizados para a interface declarativa do Jetpack Compose, garantindo a acessibilidade, o comportamento correto de estado, a navegação sem falhas e a consistência visual.

## Tecnologias e Ferramentas Utilizadas

- **Linguagem:** Kotlin
- **UI Framework:** Jetpack Compose (Material Design 3)
- **Framework de Testes de UI:** Compose UI Test Framework (`createComposeRule`, `createAndroidComposeRule`)
- **Assertion & Matchers:** `onNodeWithText`, `onNodeWithContentDescription`, `assertIsSelected`, `assertExists`
- **Ações de Teste:** `performClick`, `performScrollTo`
- **Screenshot Testing:** Captura de ecrã (*Golden Assertions*) via `AssertScreenshotMatchesGolden`
- **IDE:** Android Studio
- **Mínimo SDK:** API level 21+

## Conceitos e Aprendizados Práticos

Durante a realização deste codelab focado em testes, foram consolidados os seguintes conceitos:

### 1. Testes de Componentes Isolados com `createComposeRule()`
- Renderização de componentes isolados da aplicação (`RallyTopAppBar`, `AnimatedCircle`) no ambiente de teste sem a necessidade de lançar toda a `Activity`.
- Utilização de `setContent` dentro do escopo de teste para montar o composable em um estado específico.

### 2. Inspeção e Assertivas na Arvore da UI (*Semantics Tree*)
- Localização de nós de UI usando texto (`onNodeWithText`), descrições de conteúdo (`onNodeWithContentDescription`) e tags de teste.
- Verificação do estado de seleção das abas no `RallyTopAppBar` para validar se a navegação reflete visualmente a aba ativa (`assertIsSelected`).

### 3. Teste de Telas de Visão Geral (`OverviewScreenTest`)
- Validação da renderização correta de múltiplos cartões e resumos financeiros (Contas e Faturas).
- Interação com botões e verificação do fluxo de apresentação de dados na tela de visão geral (`OverviewBody`).

## Como Executar os Testes no Projeto

1. Clone o repositório:
   ```bash
   git clone https://github.com/leticia-farias/compose-training-testing-rally.git
2. Abra o projeto no Android Studio.
3. Aguarde a sincronização do Gradle.
4. Conecte um emulador ou dispositivo físico (API 21+).
5. Para rodar todos os testes de UI, abra o diretório app/src/androidTest/java/com/example/compose/rally/ e execute as classes:
    - TopAppBarTest.kt (Validação de abas)
    - OverviewScreenTest.kt (Validação da tela principal)
    - AnimatingCircleTests.kt (Validação de animações e Golden Tests)
