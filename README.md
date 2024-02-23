/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package lista2.exe1;

/**
 *
 * @author Vanessa
 */
public class Cliente {

    //variaveis da classe
    private String nroConta, nroAgencia, nome;
    private float saldo;

    //construtores 
    public Cliente() {

    }

    public Cliente(String nroConta, String nroAgencia, String nome, float saldo) {
         this.setNroConta(nroConta);
         this.setNroAgencia(nroAgencia);
         this.setNome(nome);
         this.setSaldo(saldo);
    }

    public final void setNroConta(String nroConta) {
        if((nroConta.length() == 8) && (nroConta.charAt(6)=='-')){
        this.nroConta = nroConta;
    }else{
            this.nroConta = "";
            System.out.println("Número da conta inválido");
    }
        
}

    public final void setNroAgencia(String nroAgencia) {
        if((nroAgencia.length()==6) && (nroAgencia.charAt(4)=='-')){
          this.nroAgencia = nroAgencia;  
        }else{
             this.nroAgencia ="";
             System.out.println("Número da Agência inválido");
            
        }
       
    }

    public final void setNome(String nome) {
        if(nome.length()<=30){
          this.nome = nome;  
        }else{
           this.nome ="";
           System.out.println("Nome inválido");
           
        }
        
    }

    public final void setSaldo(float saldo) {
        if(saldo >=0){
            this.saldo = saldo;
        }else{
             System.out.println("Saldo  não pode ficar negativo");
        }
    }

    public String getNroConta() {
        return nroConta;
    }

    public String getNroAgencia() {
        return nroAgencia;
    }

    public String getNome() {
        return nome;
    }

    public float getSaldo() {
        return saldo;
    }
    
    public void depositar(float x){
         this.setSaldo(this.saldo + x);
        
    }
    public void sacar(float x){
         this.setSaldo(this.saldo - x);
    
    }

    @Override//informa que o metodo toString ()é anulado na classe pai 
    public String toString() {
       return "Cliente{" + "nroConta=" + this.nroConta + ", nroAgencia=" + 
       this.nroAgencia + ", nome=" + this.nome + ", saldo=" + this.saldo + '}';
    }
    
}


testa.cliiente

/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */
package lista2.exe1;

/**
 *
 * @author Vanessa
 */
public class testaCliente {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        Cliente obj1= new Cliente("1235456-7", "1234-5", "Fulano", 0);
        obj1.depositar(1000);
        obj1.sacar(500);
        System.out.println(obj1.toString());
        
        Cliente obj2= new Cliente("1235456-78", "124-5", "Beltrano", 0);
        obj2.depositar(1000);
        obj2.sacar(1500);
        System.out.println(obj1.toString());
            
        
    }
    
}
