/* QuizDePerguntaseRespostas
* Iniciando um quiz de perguntas e respostas em Java
*/ 


package quiz.de.perguntas.e.respostas;

import java.util.*;
import java.lang.*;
/**
 * @author Maciel Oliveira
 */
public class QuizDePerguntasERespostas {
    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        String questao = "Quem foi o criador do Java?";
        
        Collection<String> alternativas = new ArrayList<>();
            alternativas.add("Bill Gates");
            alternativas.add("James Gosling");
            alternativas.add("Steve Jobs");
            alternativas.add("Elon Musk");
            alternativas.add("Jeff Bezos");
            
            String alternativaCorreta = "James Gosling";
            
        boolean respostaCerta = false;
        
        do {
            System.out.println(questao);
            
            //embaralhando a ordem das questões
            Collections.shuffle((List<String>) alternativas);
                               
            //Mostrando as alternativas na Tela
            
            for (int i = 0; i < alternativas.size(); i++){
                System.out.println(
                        "[" + i + "] " + ((List<String>) alternativas).get(i));
            }
                    
            System.out.println("Digite sua resposta: ");
            String resposta = scanner.nextLine();
            
            switch(resposta){
                case "0":
                case "1":
                case "2":
                case "3":
                case "4":
                    break;
                default:
                    System.out.println("Opção Inválida, Tente Novamente!");
                    break;
            }
                       
            int respostaInt = Integer.parseInt(resposta);
            
            String valorDaResposta = ((List<String>) alternativas).get(respostaInt);
                    
            if(valorDaResposta.equals(alternativaCorreta)){
                    System.out.println("Sua Resposta Está Correta"); 
                    respostaCerta = true;
            }else {
                System.out.println("Sua Resposta Está Errada! Tente Novamente");
            }
            
        } while (!respostaCerta);
    }
}



