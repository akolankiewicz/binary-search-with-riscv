# Busca Binária em RISC-V com Alocação Dinâmica

Este repositório contém a implementação do algoritmo de Busca Binária em linguagem de montagem (Assembly) RISC-V. O projeto foi desenvolvido como parte da disciplina de Organização de Computadores e inclui o uso de alocação dinâmica de memória (Heap).

## Autores
- Arthur Kolankiewicz
- Gabriel Farina

## Sobre o Projeto

O programa realiza a busca de um valor específico dentro de um array ordenado. A principal característica desta implementação é a utilização de alocação dinâmica de memória. O array, inicialmente definido na seção `.data`, é copiado para o Heap em tempo de execução antes que a busca seja realizada.

### Principais Componentes
- **Alocação Dinâmica:** Utiliza a chamada de sistema (syscall) `sbrk` (`ecall 9`) para reservar espaço no Heap.
- **Busca Binária:** Implementada na função modular `b_search`, que utiliza a convenção de chamadas do RISC-V (salvando registradores na pilha) para realizar a busca de forma eficiente.
- **Tratamento de Erros:** Caso o valor não seja encontrado, o programa retorna `-1`. Se encontrado, retorna o índice (posição) do valor no array.

## Como Executar o Programa

Para executar este código, recomendamos o uso do simulador **Venus**, que é amplamente utilizado para programas RISC-V. Siga o passo a passo abaixo:

### Passo 1: Acessar o Simulador
Você pode utilizar a versão web do Venus ou a extensão para o Visual Studio Code.
- **Versão Web:** Acesse [Venus Web Simulator](https://venus.cs61c.org/).

### Passo 2: Carregar o Código
1. No simulador Venus, vá até a aba **Editor**.
2. Copie todo o conteúdo do arquivo `programa.riscv` (ou o arquivo de código fonte fornecido) e cole no editor.

### Passo 3: Montar (Assemble) o Código
1. Após colar o código, clique na aba **Simulator** (ou no botão "Assemble & Simulate from Editor", dependendo da versão).
2. O simulador irá traduzir o código Assembly para código de máquina. Se não houver erros de sintaxe, você estará pronto para executar.

### Passo 4: Executar o Programa
1. Na aba **Simulator**, clique no botão **Run** para executar o programa inteiro de uma vez.
2. Alternativamente, você pode usar o botão **Step** para executar o código linha por linha e observar o comportamento dos registradores e da memória.

### Passo 5: Verificar o Resultado
O resultado da busca será exibido no console do simulador ou armazenado no registrador `a1`.
- **Caso de Sucesso:** Se o valor buscado (ex: `38`) estiver no array, o registrador `a1` conterá o índice correspondente (ex: `11`).
- **Caso de Falha:** Se o valor buscado (ex: `39`) não estiver no array, o registrador `a1` conterá o valor `-1`.

## Alterando os Dados de Teste
Para testar diferentes cenários, você pode modificar as seguintes variáveis na seção `.data` do código:
- `dados`: O array de números (lembre-se: **deve estar ordenado de forma crescente**).
- `alvo`: O valor que você deseja buscar.
- `tamanho`: A quantidade de elementos presentes no array.

---
*Projeto desenvolvido para fins acadêmicos.*
