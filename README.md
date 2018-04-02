# Agenda-de-Contatos-
Programa que insere, deleta e busca contatos no vetor Contatos.

public class Agenda {
	private Contato contato[];
	private int qtContato = 0;
	private int capacidade=100;
		
	public Agenda(){
		this.contato= new Contato[100];
	}

	public void setContato(Contato cont[]) {
		this.contato = cont;
	}
	
	public Contato[] getContato() {
		return this.contato;
	}
	
	public void setqtContato(int qtcont) {
		this.qtContato = qtcont;
	}
	
	public int getQtContato() {
		return this.qtContato;
	}
	
	public void setCapacidade(int cap) {
		this.capacidade = cap;
	}

	public int getCapacidade() {
		return this.capacidade;
	}

	public void InserirContato(Contato contato) {
		
		if(this.qtContato < this.capacidade) {
			this.contato[this.qtContato] = contato;
			this.qtContato++;
			
		}
		else
			System.out.println("Agenda cheia! ");
	}
  
	
	public Contato Buscar(String nome) {
		for(int i = 0; i < this.qtContato; i++) {	            // (contador; condição de parada ; anda com o contador)
			if(contato[i].getNome().equals(nome));  	
				return contato[i];
	            	
	            }
	            
	            	return null;
	}
	
	public boolean remover (String nome) {
		for (int i = 0; i < this.qtContato; i++){
	  		if(contato[i].getNome().equals(nome)){
	  			contato[i] = null;
	  			return true;
	}
		}
		return false;
	}
	
	
	public Contato buscarPorTelefone(String telefone) {
		for(int i = 0; i < this.qtContato; i++) {	            
	           if(contato[i].getTelefone().equals(telefone));
	            	return contato[i];
	            }
	            
	            	return null;
		}
	}

  public class Contato {
	private String nome;
	private String telefone;

	
	public void setNome(String nome) {
		this.nome = nome;
	}
	
	public String getNome() {
		return this.nome;
	}
	
	public void setTelefone(String telefone) {
		this.telefone = telefone;
	}
	
	public String getTelefone() {
		return this.telefone;
	}
}



public class Principal {

	public static void main(String[] args) {
		
		Agenda agenda = new Agenda();
		Contato contato1, contato2, contato3;
		contato1 = new Contato();
		contato1.setNome("Junio");
		contato1.setTelefone("12345678");
		contato2 = new Contato();
		contato2.setNome("Jessica");
		contato2.setTelefone("23456789");
		contato3 = new Contato();
		contato3.setNome("Jefferson");
		contato3.setTelefone("246810");
		
		agenda.InserirContato(contato1);
		agenda.InserirContato(contato2);
		agenda.InserirContato(contato3);
		
		System.out.println(agenda.Buscar("Junio").getNome());
		System.out.println(agenda.buscarPorTelefone("12345678").getTelefone());
		System.out.println(agenda.remover("Junio"));
    
    
	}
	
}
