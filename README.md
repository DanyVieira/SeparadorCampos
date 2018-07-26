import java.io.BufferedReader;
import java.io.File;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintWriter;

public class GerarArquivoSeparado {
	
	 public static String rtrim(String s) {
	       int i = s.length()-1;
	       while (i > 0 && Character.isWhitespace(s.charAt(i))) {
	            i--;
	       }
	       return s.substring(0,i+1);
	    }
	
	public static void main(String[] args) {
			
	
	try {
		BufferedReader br = new BufferedReader(new FileReader("C:"+File.separator+"Users"+File.separator+"daniele.ferreira"+File.separator+"Documents"+File.separator+"obitos.txt"));
		
		int contlinha=0;
		String linha ="";
		
		FileWriter arq2;
		
		
		arq2 = new FileWriter("C:"+File.separator+"Users"+File.separator+"daniele.ferreira"+File.separator+"Documents"+File.separator+"obitos2.txt");
		PrintWriter gravarArq = new PrintWriter(arq2);
	
		
		
		while(br.ready()){
			contlinha++;
			linha = br.readLine();
			String livro = linha.substring(6 - 6,6); 
			String folha = linha.substring(11 - 5,11); 
			String termo = linha.substring(21 - 10,21); 
						
			
			//String folha = linha.substring(11 - 5,11); 
			//String folha = linha.substring(11 - 5,11); 
			
			
			
			
			
			 
				gravarArq.printf("%s%s%s%s%s%s%s%s%s%s%s%s%s%n",livro+",",folha+",", termo);
			
			//}
			
			
		}
		arq2.close();
		
	} catch (IOException e) {
		// TODO Auto-generated catch block
		e.printStackTrace();
	} 

}
}
