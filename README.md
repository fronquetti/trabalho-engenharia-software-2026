# trabalho-engenharia-software-2026
Trabalho de clínica veterinária do Técnico em Informática, segundo semestre de 2026.

 LINK DO PROJETO DO FIGMA https://www.figma.com/design/KTFpXc7RjeLND2oYifGWly/Sem-t%C3%ADtulo?node-id=0-1&t=J9ZEJ6OM7xFqknCa-1

## DIAGRAMAS UML 

### Diagrama de caso de uso

```mermaid
flowchart TD
  %% atores
  cliente["cliente"]
  garçom["garçom"]

%%ações
subgraph sistema
   comida["pedir comida"]
   vinho["pedir vinho"]
end

%% relacionamentos
cliente -- "faz pedido" --- comida
garçom -- "recebe pedido" --- comida

vinho -. "estende" .-> comida
```


### Diagrama de classe
```mermaid
classDiagram
    class Veterinario{
        %% atributos: características que serão
        %% armazenamento no sitema
     -CPF: string
     %% métodos : ações que serão desempenhadas
     %% por essa entidade no sistema
     +darCPF() string
     +atenderAnimal(animal: Animal)void
    }
    Veterinario -- Animal
    Animal -- Cliente
   
class Animal{
    -dono:Cliente
    -Nome : string
    -sexo : string
    -doença: string
    -especie: string
    +Nome() string
    +sexo()string
    +doença()string
    +Especie() string
}
class Cliente{
-animais: Animal[]
-Nome: string
-contato:string
-CPF: string
+InformeNome(): string
+informeContato(): string
+InformeCPF(): string
}
```
