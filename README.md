# ATM-if
public class Main {
    public static void main(String[] args) {  
        Scanner input = new Scanner(System.in);  
        String password = "java123";  
        String userName = "patika";  
        int right = 3;  
        int select ;  
        int balance=1500;  
        int yatirilacakTutar;  
        int cekilecekTutatr;  


        while (right > 0) {

            if (right > 0) {

                System.out.print("Lütfen Kullanici ismini Giriniz : ");
                String userNameGEt = input.nextLine();

                System.out.print("Lütfen Sifrenizi Giriniz : ");
                String passworGet = input.nextLine();


                if (passworGet.equals(password) && userNameGEt.equals(userName)) {
                    do {


                        System.out.println("Hesap islemleri icin asağıdaki islemleri seciniz: " +
                                "\n 1- Bakiye Goruntuleme"
                                + "\n 2- Para Yatirma \n 3- Para Cekme \n 4- Cikis yap!");

                        select=input.nextInt();
                        System.out.println(" -- --");
                        if (select==1){
                            System.out.println("Bakiyeniz : "+ balance );
                        } else if (select==2) {
                            System.out.println("Yatiracaginiz tutari giriniz");
                            yatirilacakTutar=input.nextInt();
                            if (yatirilacakTutar>=5 && yatirilacakTutar<=10000){
                                balance+=yatirilacakTutar;

                            System.out.println("Yatirma isleminden sonra bakiyeniz:"+balance);}


                        } else if (select==3) {
                            System.out.println("cekicek tutari giriniz: ");
                            cekilecekTutatr=input.nextInt();

                            if (cekilecekTutatr>balance){
                            System.out.println("Bakiye yetersiz");}
                            else {
                                balance-=cekilecekTutatr;
                                System.out.println("Cekim isleminden sonra kalan bakiye: "+balance);
                            }

                        }
                    }


                    while (select!=4);
                    System.out.println("Cikis Yaptiniz. \n \n Tekrar bekleriz! ");
                    break;


                } else {
                    System.out.println("Sfre veya Kullanıci simi hatali tekrar deneyiniz");
                    right--;
                } System.out.println("Kalan hakkiniz : " + right);

            } if (right == 0) {
                System.out.println("İslem basarisiz kartiniz bloke olmustur! ");
                System.out.println("Bankanizla iletisime geciniz! ");
            }


        }
    }
}
