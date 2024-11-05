# 🦸‍♂️ Desafio: Classificador de Nível de Herói

## 📋 Objetivo
Cria um programa em Node.js que classifica o nível de um herói com base na quantidade de experiência (XP) que ele possui.

## 🚀 Tecnologias Utilizadas
- **Node.js** 🟢
- **Módulo Readline** para entrada de dados no terminal ⌨️

## ⚙️ Funcionamento do Código

1. **Entrada de Dados** 📥
   - O usuário insere o **nome** e a **quantidade de experiência (XP)** do herói.

2. **Classificação de Nível** 🏆
   - Com base na experiência (XP), o herói é classificado em níveis:
     - XP < 1.000 ➡️ **Ferro** 🪨
     - XP entre 1.001 e 2.000 ➡️ **Bronze** 🥉
     - XP entre 2.001 e 5.000 ➡️ **Prata** 🥈
     - XP entre 5.001 e 7.000 ➡️ **Ouro** 🥇
     - XP entre 7.001 e 8.000 ➡️ **Platina** 💎
     - XP entre 8.001 e 9.000 ➡️ **Ascendente** 🌅
     - XP entre 9.001 e 10.000 ➡️ **Imortal** 🛡️
     - XP > 10.000 ➡️ **Radiante** 🌟

3. **Exibição de Resultado** 📊
   - A mensagem final exibe o **nome** e o **nível** do herói.

## 🛠️ Código em Node.js

```javascript
const readline = require('readline');

// 🔄 Configura a interface de leitura
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

// 🦸‍♂️ Função para classificar o nível do herói com base na XP
function classificarHeroi(nome, xp) {
    let nivel;

    if (xp < 1000) {
        nivel = "Ferro 🪨";
    } else if (xp >= 1001 && xp <= 2000) {
        nivel = "Bronze 🥉";
    } else if (xp >= 2001 && xp <= 5000) {
        nivel = "Prata 🥈";
    } else if (xp >= 5001 && xp <= 7000) {
        nivel = "Ouro 🥇";
    } else if (xp >= 7001 && xp <= 8000) {
        nivel = "Platina 💎";
    } else if (xp >= 8001 && xp <= 9000) {
        nivel = "Ascendente 🌅";
    } else if (xp >= 9001 && xp <= 10000) {
        nivel = "Imortal 🛡️";
    } else {
        nivel = "Radiante 🌟";
    }

    console.log(`O Herói de nome ${nome} está no nível de ${nivel}`);
}

// 📝 Recebe os dados do usuário
rl.question("Digite o nome do herói: ", (nome) => {
    rl.question("Digite a quantidade de experiência (XP) do herói: ", (xp) => {
        classificarHeroi(nome, parseInt(xp));
        rl.close();
    });
});
