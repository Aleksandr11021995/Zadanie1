public class Main {
public static void main(String[] args) {
int[] sales = {10, 20, 30, 40, 50};
SalesManager salesManager = new SalesManager(sales);
System.out.println("Max sale: " + salesManager.max());
}
}
