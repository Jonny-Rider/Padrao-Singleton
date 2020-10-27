# Padrao-Singleton

O padrão Singleton é uma solução de design em que um aplicativo deseja ter uma e apenas uma instância de qualquer classe, em todos os cenários possíveis, sem nenhuma condição excepcional. Já foi debatido por muito tempo na comunidade java sobre as possíveis abordagens para fazer qualquer classe única. Ainda assim, você encontrará pessoas insatisfeitas com qualquer solução que você der. Eles também não podem ser anulados. 

O termo singleton é derivado de sua contraparte matemática. Ele quer que, como dito acima, tenhamos apenas uma instância por contexto. Em Java, uma instância por JVM.

Modelo de código abaixo projetando sua classe singleton que deve garantir apenas uma instância de uma classe em todo o aplicativo em todos os cenários.

    public class DemoSingleton implements Serializable {

    private static final long serialVersionUID = 1L;
 
    private DemoSingleton() {
        // private constructor
    }
 
    private static class DemoSingletonHolder {
        public static final DemoSingleton INSTANCE = new DemoSingleton();
    }
 
    public static DemoSingleton getInstance() {
        return DemoSingletonHolder.INSTANCE;
    }
 
    protected Object readResolve() {
        return getInstance();
    }
}
