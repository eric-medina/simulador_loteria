# Simulador de Loteria
Este projeto é um simulador da Mega-Sena, onde o usuário digita seis números e são sorteados aleatoriamente outros seus números, que são comparados com os números informados pelo usuário, verificando o número de acertos.

*Não é para jogos oficiais*

## Tecnologias utilizadas

1. *HTML*: HTML (abreviação para a expressão inglesa HyperText Markup Language, que significa Linguagem de Marcação de Hipertexto) é uma linguagem de marcação utilizada na construção de páginas na Web.
2. *CSS*: Cascading Style Sheets (CSS) é um mecanismo para adicionar estilo (cores, fontes, espaçamento, etc.) a um documento web.
3. *JS*: JavaScript (frequentemente abreviado como JS) é uma linguagem de programação interpretada estruturada, de script em alto nível com tipagem dinâmica fraca e multiparadigma (protótipos, orientado a objeto, imperativo e, funcional).
4. ~~**jQuery**~~: Não foi utilizado.

## Funções Principais
Aqui serão apresentadas as duas funções principais do site.

### Sorteio de números
Nessa função os números são sorteados aleatoriamente.
```
function Sorteio(){
	let num= Math.floor(Math.random() * 60);
	let li = document.createElement("li");
    for (var i = 0; i < 6; i++){
		numSort[i] =num;
		if(numSort[i]<=9){
			numSort[i]='0'+numSort[i];
		}else{
			numSort[i]=''+numSort[i];
		}
		num= Math.floor(Math.random() * 60);
		while(numSort.indexOf(num)!=-1){
			num= Math.floor(Math.random() * 60);
		  }
    }
	for (var i = 0; i < 6; i++){
		li = document.createElement("li");
		li.innerHTML = numSort[i];
		document.getElementById("numSort").append(li);
	}
}
```

### Lendo os números digitados
Lê as entradas de números digitados pelo usuário.
```
function addToList(num, pos){
    if(num.length == 2){
        if(numEsco.indexOf(num)!=-1){
            alert2("Erro","Número escolhido anteriormente. Digite outro número")
        }else if(parseInt(num)>60){
            alert2("Erro", "O números digitado não pode ser maior que 60")
        }else{
            numEsco[pos] = num;
        }
    }
}
```

## Como rodar o código
> Simplesmente baixe o código e abra o arquivo **_index.html_** no seu navegador.

## Exemplo de tabela
| Exemplo   | Valor do exemplo | Quantidade
| --------- | ---------------- | ----------
| Exemplo 1 | R$ 10            | 5
| Exemplo 2 | R$ 8             | 4
| Exemplo 3 | R$ 7             | 34
| Exemplo 4 | R$ 8             | 23

## Imagens da tela
Tela 1: Tela de abertura.
![Tela 1](/imagens/tela1.png)
Tela 2: 6 números sorteados.
![](/imagens/tela2.png)
#### Referências
* HTML: [Wikipedia](https://pt.wikipedia.org/wiki/HTML)
* CSS: [Wikipedia](https://pt.wikipedia.org/wiki/Cascading_Style_Sheets)
* JavaScript: [Wikipedia](https://pt.wikipedia.org/wiki/JavaScript)
