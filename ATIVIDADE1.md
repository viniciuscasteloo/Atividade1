import java.util.Scanner;

public class Main {

    static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) {
        int opcao;

        do {
            System.out.println("\n===== MENU PRINCIPAL =====");
            System.out.println("0.  Sair");
            System.out.println("1.  Par ou Ímpar");
            System.out.println("2.  Maior de Dois");
            System.out.println("3.  Calculadora com Menu");
            System.out.println("4.  Validação de Entrada");
            System.out.println("5.  Sentinela (parada no 0)");
            System.out.println("6.  Simulador de Caixa");
            System.out.println("7.  Desconto por Categoria");
            System.out.println("8.  Contagem de Valores");
            System.out.println("9.  Soma de 1 até N");
            System.out.println("10. Contagem Regressiva e Soma");
            System.out.print("Escolha uma opção: ");
            opcao = sc.nextInt();

            switch (opcao) {
                case 0 -> System.out.println("Saindo... Até logo!");
                case 1 -> exercicio1();
                case 2 -> exercicio2();
                case 3 -> exercicio3();
                case 4 -> exercicio4();
                case 5 -> exercicio5();
                case 6 -> exercicio6();
                case 7 -> exercicio7();
                case 8 -> exercicio8();
                case 9 -> exercicio9();
                case 10 -> exercicio10();
                default -> System.out.println("Opção inválida! Tente novamente.");
            }

        } while (opcao != 0);
    }

    // ─────────────────────────────────────────────────────────────────
    // Exercício 1 – Par ou Ímpar
    // ─────────────────────────────────────────────────────────────────
    static void exercicio1() {
        System.out.println("\n--- Exercício 1: Par ou Ímpar ---");
        System.out.print("Digite um número inteiro: ");
        int n = sc.nextInt();
        if (n % 2 == 0) {
            System.out.println("PAR");
        } else {
            System.out.println("ÍMPAR");
        }
    }

    // ─────────────────────────────────────────────────────────────────
    // Exercício 2 – Maior de Dois
    // ─────────────────────────────────────────────────────────────────
    static void exercicio2() {
        System.out.println("\n--- Exercício 2: Maior de Dois ---");
        System.out.print("Digite o primeiro número: ");
        int a = sc.nextInt();
        System.out.print("Digite o segundo número: ");
        int b = sc.nextInt();

        if (a > b) {
            System.out.println("O maior é: " + a);
        } else if (b > a) {
            System.out.println("O maior é: " + b);
        } else {
            System.out.println("Iguais");
        }
    }

    // ─────────────────────────────────────────────────────────────────
    // Exercício 3 – Calculadora com Menu
    // ─────────────────────────────────────────────────────────────────
    static void exercicio3() {
        System.out.println("\n--- Exercício 3: Calculadora ---");
        System.out.println("1- Somar");
        System.out.println("2- Subtrair");
        System.out.println("3- Multiplicar");
        System.out.println("4- Dividir");
        System.out.print("Escolha a operação: ");
        int op = sc.nextInt();

        System.out.print("Digite o primeiro número: ");
        double x = sc.nextDouble();
        System.out.print("Digite o segundo número: ");
        double y = sc.nextDouble();

        switch (op) {
            case 1 -> System.out.printf("Resultado: %.2f%n", x + y);
            case 2 -> System.out.printf("Resultado: %.2f%n", x - y);
            case 3 -> System.out.printf("Resultado: %.2f%n", x * y);
            case 4 -> {
                if (y == 0) {
                    System.out.println("Erro: divisão por zero não é permitida!");
                } else {
                    System.out.printf("Resultado: %.2f%n", x / y);
                }
            }
            default -> System.out.println("Operação inválida!");
        }
    }

    // ─────────────────────────────────────────────────────────────────
    // Exercício 4 – Validação de Entrada
    // ─────────────────────────────────────────────────────────────────
    static void exercicio4() {
        System.out.println("\n--- Exercício 4: Validação de Nota ---");
        double nota;
        do {
            System.out.print("Digite uma nota entre 0 e 100: ");
            nota = sc.nextDouble();
            if (nota < 0 || nota > 100) {
                System.out.println("Nota inválida! Tente novamente.");
            }
        } while (nota < 0 || nota > 100);
        System.out.printf("Nota aceita: %.1f%n", nota);
    }

    // ─────────────────────────────────────────────────────────────────
    // Exercício 5 – Sentinela (parada no 0)
    // ─────────────────────────────────────────────────────────────────
    static void exercicio5() {
        System.out.println("\n--- Exercício 5: Sentinela ---");
        System.out.println("Digite números (0 para encerrar):");

        int maior = Integer.MIN_VALUE;
        int menor = Integer.MAX_VALUE;
        boolean algumNumero = false;

        while (true) {
            System.out.print("Número: ");
            int num = sc.nextInt();
            if (num == 0) break;

            algumNumero = true;
            if (num > maior) maior = num;
            if (num < menor) menor = num;
        }

        if (algumNumero) {
            System.out.println("Maior: " + maior);
            System.out.println("Menor: " + menor);
        } else {
            System.out.println("Nenhum número foi digitado.");
        }
    }

    // ─────────────────────────────────────────────────────────────────
    // Exercício 6 – Simulador de Caixa
    // ─────────────────────────────────────────────────────────────────
    static void exercicio6() {
        System.out.println("\n--- Exercício 6: Simulador de Caixa ---");
        double saldo = 1000.00;
        int op;

        do {
            System.out.println("\n1- Depositar");
            System.out.println("2- Sacar");
            System.out.println("3- Ver saldo");
            System.out.println("4- Sair");
            System.out.print("Opção: ");
            op = sc.nextInt();

            switch (op) {
                case 1 -> {
                    System.out.print("Valor do depósito: R$ ");
                    double deposito = sc.nextDouble();
                    if (deposito > 0) {
                        saldo += deposito;
                        System.out.printf("Depósito realizado. Saldo atual: R$ %.2f%n", saldo);
                    } else {
                        System.out.println("Valor de depósito inválido! Deve ser maior que zero.");
                    }
                }
                case 2 -> {
                    System.out.print("Valor do saque: R$ ");
                    double saque = sc.nextDouble();
                    if (saque <= 0) {
                        System.out.println("Valor inválido! O saque deve ser maior que zero.");
                    } else if (saque > saldo) {
                        System.out.println("Saldo insuficiente!");
                    } else {
                        saldo -= saque;
                        System.out.printf("Saque realizado. Saldo atual: R$ %.2f%n", saldo);
                    }
                }
                case 3 -> System.out.printf("Saldo atual: R$ %.2f%n", saldo);
                case 4 -> System.out.printf("Saindo... Saldo final: R$ %.2f%n", saldo);
                default -> System.out.println("Opção inválida!");
            }
        } while (op != 4);
    }

    // ─────────────────────────────────────────────────────────────────
    // Exercício 7 – Desconto por Categoria
    // ─────────────────────────────────────────────────────────────────
    static void exercicio7() {
        System.out.println("\n--- Exercício 7: Desconto por Categoria ---");
        System.out.print("Valor da compra: R$ ");
        double valorCompra = sc.nextDouble();

        System.out.println("Categoria: 1 = Comum | 2 = Premium | 3 = Funcionário");
        System.out.print("Categoria do cliente: ");
        int categoria = sc.nextInt();

        double percentual;

        switch (categoria) {
            case 1 -> percentual = 0.05;
            case 2 -> percentual = 0.10;
            case 3 -> percentual = 0.15;
            default -> {
                System.out.println("Categoria inválida.");
                return;
            }
        }

        double desconto = valorCompra * percentual;
        double valorFinal = valorCompra - desconto;

        System.out.printf("Desconto (%.0f%%): R$ %.2f%n", percentual * 100, desconto);
        System.out.printf("Valor final a pagar: R$ %.2f%n", valorFinal);
    }

    // ─────────────────────────────────────────────────────────────────
    // Exercício 8 – Contagem de Valores
    // ─────────────────────────────────────────────────────────────────
    static void exercicio8() {
        System.out.println("\n--- Exercício 8: Contagem de Valores ---");
        int positivos = 0, negativos = 0, zeros = 0;

        for (int i = 1; i <= 10; i++) {
            System.out.print("Digite o " + i + "º número: ");
            int num = sc.nextInt();
            if (num > 0) positivos++;
            else if (num < 0) negativos++;
            else zeros++;
        }

        System.out.println("Positivos: " + positivos);
        System.out.println("Negativos: " + negativos);
        System.out.println("Zeros:     " + zeros);
    }

    // ─────────────────────────────────────────────────────────────────
    // Exercício 9 – Soma de 1 até N
    // ─────────────────────────────────────────────────────────────────
    static void exercicio9() {
        System.out.println("\n--- Exercício 9: Soma de 1 até N ---");
        System.out.print("Digite N: ");
        int n = sc.nextInt();

        long soma = 0;
        for (int i = 1; i <= n; i++) {
            soma += i;
        }

        System.out.println("Soma de 1 até " + n + " = " + soma);
    }

    // ─────────────────────────────────────────────────────────────────
    // Exercício 10 – Contagem Regressiva e Soma
    // ─────────────────────────────────────────────────────────────────
    static void exercicio10() {
        System.out.println("\n--- Exercício 10: Contagem Regressiva e Soma ---");
        int n;
        do {
            System.out.print("Digite N (deve ser maior que 0): ");
            n = sc.nextInt();
            if (n <= 0) System.out.println("Valor inválido! N deve ser maior que 0.");
        } while (n <= 0);

        long soma = 0;
        StringBuilder contagem = new StringBuilder();

        for (int i = n; i >= 1; i--) {
            contagem.append(i);
            if (i > 1) contagem.append(" ");
            soma += i;
        }

        System.out.println(contagem);
        System.out.println("Soma = " + soma);
    }
}
