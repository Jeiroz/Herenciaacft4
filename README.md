// Clase abstracta Producto
abstract class Producto {
    protected String nombre;
    protected double precio;
    
    public Producto(String nombre, double precio) {
        this.nombre = nombre;
        this.precio = precio;
    }
    
    public abstract void mostrarDetalles();
}

// Subclase Electrónico
class Electronico extends Producto {
    private String marca;
    
    public Electronico(String nombre, double precio, String marca) {
        super(nombre, precio);
        this.marca = marca;
    }
    
    @Override
    public void mostrarDetalles() {
        System.out.println("Electrónico: " + nombre + ", Precio: $" + precio + ", Marca: " + marca);
    }
}

// Subclase Alimento
class Alimento extends Producto {
    private String fechaExpiracion;
    
    public Alimento(String nombre, double precio, String fechaExpiracion) {
        super(nombre, precio);
        this.fechaExpiracion = fechaExpiracion;
    }
    
    @Override
    public void mostrarDetalles() {
        System.out.println("Alimento: " + nombre + ", Precio: $" + precio + ", Expira el: " + fechaExpiracion);
    }
}

// Subclase Ropa
class Ropa extends Producto {
    private String talla;
    
    public Ropa(String nombre, double precio, String talla) {
        super(nombre, precio);
        this.talla = talla;
    }
    
    @Override
    public void mostrarDetalles() {
        System.out.println("Ropa: " + nombre + ", Precio: $" + precio + ", Talla: " + talla);
    }
}

// Clase principal Main
public class Main {
    public static void main(String[] args) {
        Producto[] productos = {
            new Electronico("Laptop", 15000, "Dell"),
            new Alimento("Manzana", 15, "01/04/2025"),
            new Ropa("Camisa", 500, "M")
        };
        
        for (Producto producto : productos) {
            producto.mostrarDetalles();
        }
    }
}
