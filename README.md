# trabalho-engenharia-software-2026
Trabalho de clínica veterinária do Técnico em Informática, segundo semestre de 2026.

 LINK DO PROJETO DO FIGMA https://www.figma.com/design/KTFpXc7RjeLND2oYifGWly/Sem-t%C3%ADtulo?node-id=0-1&t=J9ZEJ6OM7xFqknCa-1

## DIAGRAMAS UML 

### Diagrama de caso de uso

```mermaid
flowchart TD
 veterinario["veterinário"]
tutor["tutor"]

%% ações
subgraph sistema
   cadastrarTutor["cadastrar dados do tutor"]
   cadastrarAnimal["cadastrar dados e sintomas do animal"]
   agendarConsulta["agendar consulta"]
   consultarAnimal["consultar animal"]
end

%% relacionamentos
veterinario -- "preenche" --- cadastrarTutor
tutor -- "informa dados" --- cadastrarTutor

veterinario -- "preenche" --- cadastrarAnimal
tutor -- "informa dados" --- cadastrarAnimal

veterinario -- "realiza" --- agendarConsulta
veterinario -- "consulta" --- consultarAnimal

cadastrarTutor -. "possui" .-> cadastrarAnimal
agendarConsulta -. "é referente ao" .-> cadastrarAnimal
consultarAnimal -. "após" .-> agendarConsulta
```


### Diagrama de classe
```mermaid
classDiagram
  class Veterinario {
   +preencherDados()
   +agendarConsulta()
   +atenderAnimal(animal: Animal)void
}

class Tutor {
    -animais: Animal[]
   -nome : String
   -telefone : String
   -cpf : String
}

class Animal {
    -dono: Cliente
   -nome : String
   -especie : String
   -sexo : String
   -sintomas : String
   -vacinacaoEmDia : boolean
}

class Consulta {
   -data : String
   -horario : String
   -procedimento : String
}

Veterinario --> Tutor : cadastra
Veterinario --> Animal : cadastra
Veterinario --> Consulta : agenda
Tutor --> Animal : informa dados
```
