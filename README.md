# sem11

public class Estudiante {
    private String id;
    private String nombre;
    private int edad;

    public Estudiante(String id, String nombre, int edad) {
        this.id = id;
        this.nombre = nombre;
        this.edad = edad;
    }

    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public int getEdad() {
        return edad;
    }

    public void setEdad(int edad) {
        this.edad = edad;
    }
   
}

public class EjemploColeccion {

 
    public static void main(String[] args) {
      //Generar instancias del tipo Estudiante
      
      Estudiante e1=new Estudiante("001", "Jean", 25);
      Estudiante e2=new Estudiante("002", "Pablo", 22);
      Estudiante e3=new Estudiante("003", "Juan", 21);
      Estudiante e4=new Estudiante("004", "Juana", 26);
      Estudiante e5=new Estudiante("005", "Maria", 29);
      
      //Genear una instancia de tipo ArrayList
      
      ArrayList<Estudiante> Salon = new ArrayList<Estudiante>();
      
      //agregamos las intancias estudiante al array list salon
      
      Salon.add(e1);
      Salon.add(e2);
      Salon.add(e3);
      Salon.add(e4);
      Salon.add(e5);
      
      //Generar una instancia del tipo Iterator para el recorrido
      Iterator<Estudiante> itr = Salon.iterator();
      
      while(itr.hasNext()){
      Estudiante est= (Estudiante)itr.next();
          System.out.println(est.getId()+"\t" + est.getNombre()+ "\t" + est.getEdad());
      
      }
      
    }

    public abstract class Persona {
    private int dni;
    private String nombre;
    private String genero;

    public Persona() {
    }

    public Persona(int dni, String nombre, String genero) {
        this.dni = dni;
        this.nombre = nombre;
        this.genero = genero;
    }

    @Override
    public String toString() {
        return "\n>> Informacion de Persona: "+
                "\n DNI: " +this.dni+
                "\n Nombre: " +this.nombre+
                "\n Genero: " +this.genero;
    }
    
   
    public int getDni() {
        return dni;
    }

    public void setDni(int dni) {
        this.dni = dni;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public String getGenero() {
        return genero;
    }

    public void setGenero(String genero) {
        this.genero = genero;
    }
    
    
}

public class Vehiculo {
    private String marca;
    private String modelo;
    private String tipo;

    public Vehiculo() {
    }

    public Vehiculo(String marca, String modelo, String tipo) {
        this.marca = marca;
        this.modelo = modelo;
        this.tipo = tipo;
    }

    @Override
    public String toString() {
         return "\n>> Informacion de Vehículo: "+
                "\n Marca del Vehículo: " +this.marca+
                "\n Nombre del Vehículo: " +this.modelo+
                "\n Tipo del Vehículo: " +this.tipo;
    }

    public String getMarca() {
        return marca;
    }

    public void setMarca(String marca) {
        this.marca = marca;
    }

    public String getModelo() {
        return modelo;
    }

    public void setModelo(String modelo) {
        this.modelo = modelo;
    }

    public String getTipo() {
        return tipo;
    }

    public void setTipo(String tipo) {
        this.tipo = tipo;
    }

    
    
    
}

public class Piloto extends Persona {
    private String nombreEquipo;
    private String codLicencia;
    private int aniosExpe;
    
    private Vehiculo algunVehiculo;

    public Piloto() {
    }

    public Piloto(int dni, String nombre, String genero,String nombreEquipo, String codLicencia, int aniosExpe, Vehiculo algunVehiculo) {
        super(dni,nombre,genero);
        this.nombreEquipo = nombreEquipo;
        this.codLicencia = codLicencia;
        this.aniosExpe = aniosExpe;
        this.algunVehiculo = algunVehiculo;
    }

    

    @Override
    public String toString() {
         return "\n>> Informacion del Piloto: "+
                "\n Nombre del Equipo: " +this.nombreEquipo+
                "\n Codigo del Piloto: " +this.codLicencia+
                "\n Años de Experiencia: " +this.aniosExpe+
                 super.toString()+
                algunVehiculo.toString();
    }

    public String getNombreEquipo() {
        return nombreEquipo;
    }

    public void setNombreEquipo(String nombreEquipo) {
        this.nombreEquipo = nombreEquipo;
    }

    public String getCodLicencia() {
        return codLicencia;
    }

    public void setCodLicencia(String codLicencia) {
        this.codLicencia = codLicencia;
    }

    public int getAniosExpe() {
        return aniosExpe;
    }

    public void setAniosExpe(int aniosExpe) {
        this.aniosExpe = aniosExpe;
    }

    public Vehiculo getAlgunVehiculo() {
        return algunVehiculo;
    }

    public void setAlgunVehiculo(Vehiculo algunVehiculo) {
        this.algunVehiculo = algunVehiculo;
    }
    
    
}

import java.util.ArrayList;
import java.util.Iterator;


public class Ejecutor {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        //Instacnias del tipo Vehiculo
      Vehiculo ve1=new Vehiculo("Toyota", "Yaris", "Sedan");
      Vehiculo ve2=new Vehiculo("Chevrolet", "N400 Moive", "Minit");
      Vehiculo ve3=new Vehiculo("Hyunday", "Tucson", "Suv");
      Vehiculo ve4=new Vehiculo("Nissan", "C343", "Regob");
      Vehiculo ve5=new Vehiculo("Ferrari", "Jaguar", "Race");
        
        //Instancias del tipo Piloto
        Piloto p1= new Piloto (54,"Holas","sda","Equipo Warrior","Lic25-0043",12,ve1);
        Piloto p2= new Piloto (54,"Holas","sda","Equipo Alfa","Lic25-0056",6,ve2);
        Piloto p3= new Piloto (54,"Holas","sda","Equipo Beta","Lic25-0034",11,ve3);
        Piloto p4= new Piloto (54,"Holas","sda","Equipo Sigma","Lic25-0023",8,ve4);
        Piloto p5= new Piloto (54,"Holas","sda","Equipo Delta","Lic25-0144",15,ve5);

        ArrayList<Piloto> equipoCompetencia = new ArrayList<Piloto>();
          
        equipoCompetencia.add(p1);
        equipoCompetencia.add(p2);
        equipoCompetencia.add(p3);
        equipoCompetencia.add(p4);
        equipoCompetencia.add(p5);
        
        //Instancias del tipo Iterator
        Iterator<Piloto> itr = equipoCompetencia.iterator();
        

        while (itr.hasNext()){
        Piloto pil = (Piloto)itr.next();
            System.out.println(pil.toString());
        }
    }
    
}
