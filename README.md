# Sorteia-Nomes
Sorteador de nomes aleatórios, com menu interativo

<?php

//array para guardar lista de nomes
$nomes = [];


do {

    echo "Menu de opções:\n";

    echo " 1 - Adicionar\n";

    if (count($nomes) >= 1) echo " 2 - Listar\n";

    if (count($nomes) >= 2) echo " 3 - Sortear\n";
    echo " 4 - Sair\n";

    //opção selecionada pelo usuário
    $opcao = readline('Digite a opção desejada. ');
    echo "\n\n";


    //validação das opções
    switch ($opcao) {
        //adicionar
        case 1:
            $nomes[] = readline('Digite um novo nome.');
            echo "\n";
            break;

        //listar
        case 2:
            if (count($nomes) >= 1) {
                echo "Lista de nomes. \n";
                foreach ($nomes as $nome) {
                    echo " - " . $nome . "\n";
                }
                echo "\n\n";
            }
            break;

            //sorteio da posiçao do array
            case 3:
            if (count($nomes) >= 2) {
            $indice = array_rand($nomes);
            //nome sorteado
            echo "Nome sorteado: " .$nomes[$indice];
                echo "\n\n";
                //remove os nomes ja sorteados
                unset($nomes[$indice]);
            }
            break;

}
} while($opcao !=4);
