public class SalesManager {
    private long[] sales;

    public SalesManager(long[] sales) {
        this.sales = sales;
    }

    public long getMaxSales() {
        long maxSales = sales[0];
        for (int i = 1; i < sales.length; i++) {
            if (sales[i] > maxSales) {
                maxSales = sales[i];
            }
        }
        return maxSales;
    }

    public double getTrimmedMeanSales() {
        long minSales = sales[0];
        long maxSales = sales[0];
        long sumSales = 0;
        for (int i = 0; i < sales.length; i++) {
            if (sales[i] < minSales) {
                minSales = sales[i];
            }
            if (sales[i] > maxSales) {
                maxSales = sales[i];
            }
            sumSales += sales[i];
        }
        return (double)(sumSales - minSales - maxSales) / (sales.length - 2);
    }

    public static void main(String[] args) {
        long[] sales = { 10, 20, 30, 40, 50 };
        SalesManager manager = new SalesManager(sales);
        System.out.println(manager.getMaxSales());
        System.out.println(manager.getTrimmedMeanSales());
    }
}
