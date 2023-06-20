---
marp: true
theme: gaia
backgroundColor: white
color: black
paginate: true
footer: Sistemas Operacionais Desktop - Fabrício Barros Cabral <<fabricio.cabral@ead.ifpe.edu.br>>
---
<style>
img[alt~="center"] {
    display: block;
    margin: 0 auto;
}

kbd {
  background-color: #fafbfc;
  border: thin solid #d1d5da;
  border-bottom-color: #c6cbd1;
  border-radius: 0.2em;
  box-shadow: inset 0 -1px 0 #c6cbd1;
  color: #444d56;
  display: inline-block;
  font: 1em monospace;
  padding: 3px 5px;
  vertical-align: middle;
}
</style>

<!-- _paginate: false -->
# **Sistemas Operacionais Desktop**

## Aula 4 - Gerenciamento de Memória e Memória Virtual

---

## Gerenciamento de Memória

- É um complexo campo da ciência da computação e são constantemente desenvolvidas várias técnicas para torná-la mais eficiente. Em sua forma mais simples, está relacionado em duas tarefas essenciais:
  - **Alocação**: quando o programa requisita um bloco de memória, o gerenciador o disponibiliza para a alocação
  - **Reciclagem**: quando um bloco de memória foi alocado e não é mais utilizado, esse bloco é liberado e pode ser reutilizado para outra requisição

---

## Gerenciamento de Memória

- O gerenciamento de memória é desenvolvido a partir de duas tarefas:
  - **Alocação**: pode ser tanto estática, feita quando o programa é compilado, e a dinâmica, adiada até a execução
  - **Fragmentação** (desperdício de memória): pode ser interna, sobra na memória reservada ao programa, e externa que acontece quando após o termino dos programas são deixadas pequenas lacunas entre as páginas

---

## Gerenciamento de Memória

- Para que a utilização da memória seja mais vantajosa, é utilizada a **Paginação**, processos virtuais da memória, aplicados na divisão da memória física em partições menores, chamadas de **frames**. O conjunto de registradores especiais rápidos chama-se **Translation Lookaside Buffer**, estes são subdivididos em chave/valor que lhe é dado em todos os registradores ao mesmo tempo, e valor.
- Existe uma técnica de gerencia de memória chamada memória virtual, que é onde memórias principais e secundárias juntas criam a ilusão de que há muito mais memória.

---

## Gerenciamento de Memória

- A alocação de memória está dividida em três partes: Alocação Estática, Alocação Dinâmica e Alocação Local
- **Alocação Estática**: decisão tomada quando o programa é compilado. Quando o programa é executado o Sistema operacional o lê e cria um processo, sendo o programa uma noção estática e o processo o programa em execução, que é criado em armazenamento primário e após isso recebe um espaço na memória

---

## Gerenciamento de Memória

- **Alocação Dinâmica**: decisão é adiada até a execução. Os objetos alocados dinamicamente podem ser criados e liberados a qualquer momento, em qualquer ordem, o que difere dos objetos locais das funções, que são criados e destruídos em uma ordem específica. A memória reservada para objetos dinâmica costuma ser chamada de heap
- **Alocação Local**: este processo de alocação é usado para variáveis que são locais a funções e sub-rotinas. Isso significa que o processo em execução deve manter acessível as variáveis locais da função ou procedimento que está executando no momento

---

## Gerenciamento de Memória

- **Fragmentação** (desperdício de espaço disponível em memória) pode ser de dois tipos: Interna e Externa
- **Interna**: ocorre quando o processo não ocupa inteiramente os blocos de memória (páginas) reservados para ele. Geralmente acontece pois o tamanho do processo não é um múltiplo do tamanho da página de memória, o que acarreta sobra de espaço na última página alocada (dentro de um processo)

---

## Gerenciamento de Memória

- **Externa**: ocorre à medida que os programas vão terminando e deixando lacunas cada vez menores de espaços entre as páginas. Dependendo do tamanho que precisa ser escrito em memória, estes espaços podem ser pequenos demais para serem úteis, e assim ficam inutilizados (entre processos)

---

## Gerenciamento de Memória

- Paginação
  - É um processo de virtualização da memória que consiste na subdivisão da memória física em pequenas partições (frames), para permitir uma utilização mais eficiente da mesma. A alocação de memória é requisitada por páginas, a menor unidade deste método. Cada página é mapeada num frame de memória através de um processo chamado de paginação
  
---

## Referências Bibliográficas

- MAZIERO, C. "Sistemas Operacionais: Conceitos e Mecanismos". Editora da UFPR, 2019. 456 p. ISBN 978-85-7335-340-2, https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start, acessado em 09/05/2023
- Tanenbaum, A. "Sistemas Operacionais Modernos, 3ª edição". São Paulo: Pearson Prentice Hall, 2010.
- Wikipedia. "Gerenciamento de memória". https://pt.wikipedia.org/wiki/Gerenciamento_de_mem%C3%B3ria, acessado em 24/05/2023
