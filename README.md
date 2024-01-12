# ebac_mod_17 LESS

**Comandos**

`npm init -y`

`npm install --save-dev less`

`npm run less`

`npm i -g less-watch-compiler`

`npm i --save-dev less-watch-compiler`



>Acesse no link a  seguir os ícones do site que usamos na aula 

>[*Link* - Feathericons](https://feathericons.com/.)

>[*Link* - Flatuicolors](https://flatuicolors.com/)


```
Declaração de mixins: 
Para criar um mixin, use o nome do mixin e os estilos que deseja incluir. 
Por exemplo: 
.name {  
    propriedade: valor;  // ... 
    }

Parâmetros de mixins: 
Os mixins podem aceitar parâmetros para torná-los mais flexíveis e reutilizáveis. Para definir parâmetros, coloque-os entre parênteses na declaração do mixin. Por exemplo: 
.mixin-name(@param1, @param2) 
{  
    propriedade: @param1;  // ... 
}

Passagem de argumentos para mixins: 
Ao usar um mixin que possui parâmetros, você pode passar valores para esses parâmetros ao incluir o mixin. Por exemplo: 
.selector {  
    .mixin-name(valor1, valor2); 
    }

    Valores padrão para parâmetros: 
    Você pode definir valores padrão para os parâmetros de um mixin, caso nenhum valor seja fornecido ao usá-lo. Para isso, atribua um valor padrão aos parâmetros na declaração do mixin. Por exemplo: 
    .mixin-name(@param: valor-padrão) 
    {  
        propriedade: @param;  // ...
     }


Mixins com regras condicionais: 
É possível usar lógica condicional, como when e if, dentro dos mixins para criar comportamentos dinâmicos com base nos valores dos parâmetros ou outras condições.

Mixins aninhados: 
Você pode aninhar mixins dentro de outros mixins para criar estruturas de estilos mais complexas e reutilizáveis.

Importação de mixins: 
Se você definir mixins em um arquivo separado, pode importá-los em outros arquivos Less usando a diretiva @import.

```
~~~
Translate: 
transform(translateX(100px)); 
transform(translateY(-50%)); 
transform(translate(50px, -20px));
~~~
~~~
Rotate: 
transform(rotate(45deg)); 
transform(rotateX(180deg)); 
transform(rotateY(90deg));
~~~
~~~
Scale: 
transform(scale(1.5)); 
transform(scaleX(0.8)); 
transform(scaleY(1.2)); 
transform(scale(0.5, 1.2));
~~~
~~~
Skew: 
transform(skewX(10deg)); 
transform(skewY(-20deg)); 
transform(skew(10deg, -20deg));
~~~

**Declare um map:**
```
Para criar um map utilizar o @ antes do nome do map:
 @cores: {  
    Primaria: red;  
    Secundária: blue;
     }
```
**Acesso a valores do map:**
```
Para acessar um valor específico de um map, utilize a notação de colchetes [] com a chave correspondente. Por exemplo: 
@map: (  chave1: valor1,  chave2: valor2,  // ... ); 
.selector {  propriedade: @map[chave1]; }

```

**Iteração sobre um map:**
```
É possível percorrer todos os pares chave-valor de um map usando uma diretiva each. Por exemplo: 

@map: (  
    chave1: valor1,  
    chave2: valor2,  
    // ... ); 
.selector {  
    each(@map, {    
        @key: @value;    
// Fazer algo com a chave e o valor  
}); }

```

**Atualização de valores do map:**

```
Você pode atualizar ou adicionar novos valores a um map atribuindo um novo valor a uma chave existente ou adicionando uma nova chave-valor. Por exemplo: 
@map: (  
    chave1: valor1,  
    chave2: valor2,  
    // ... 
    ); 
    @map[chave1]: novo-valor; 
    @map[chave3]: valor3;

```

**Uso de maps com mixins:**
```
Os maps são especialmente úteis quando combinados com mixins. 
Você pode passar um map como argumento para um mixin e utilizar os valores correspondentes dentro do mixin. Isso permite criar mixins altamente flexíveis e configuráveis.
```
**Sobre o escaping**
```
Trata-se de um recurso do LESS usado para armazenar uma string que poderá ser utilizada para construir uma regra de estilo. 
É feito usando o caractere ~ (til) 
seguido do valor ou expressão que deseja escapar. 
Exemplo: 
@desktopBreakpoint: ~”(min-width: 1023px)”; // escaping 
@media @desktopBreakpoint{ // @media (min-width: 1023px)     
body {          
    font-size: 1.2em;
 } 
 }

```

**Sobre os mixins**
```
Com os mixins podemos escrever porções de estilos que 
iremos reutilizar em diversos seletores. 
Para escrever um mixin seguimos a estrutura:
.nomeDoMixin( ) {       
    // Estilização 
    }
.classe {      
    .nomeDoMixin( ); 
    // utilização 
    }

```