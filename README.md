# ATMBankifElse
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        String userName, password;
        int right = 3;
        int balance = 1500;
        int select;

        Scanner input = new Scanner(System.in);


        while (right > 0) {

            System.out.println("Kullanici adinizi giriniz : ");
            userName = input.nextLine();

            System.out.println("Sifrenizi giriniz : ");
            password = input.nextLine();

            if (userName.equals("patika") && password.equals("dev123")) {
                System.out.println("Merhaba Kodluyoruz Bank a hosgeldiniz : ");
                do {
                    System.out.println("Lutfen yapmak istediginiz islemi seciniz : ");
                    System.out.println("1- para yatirma\n" +
                            "2-para cekme \n" +
                            "3- Bakiye sorgulama\n" +
                            "4- Cikis yap");
                    select = input.nextInt();

                    if (select == 1) {
                        System.out.println("Para miktari : ");
                        int price = input.nextInt();
                        balance = balance + price;
                        System.out.println("Toplam paraniz : " + balance);
                    } else if (select == 2) {
                        System.out.println("Para miktari : ");
                        int price = input.nextInt();
                        if (price > balance) {
                            System.out.println("Hesabinizde yeterli baliye bulunmamaktadir");
                        } else {
                            balance = balance - price;
                            System.out.println("Kalan paraniz : " + balance);
                        }
                    } else if (select == 3) {
                        System.out.println("Bakiyeniz : " + balance);
                    }
                } while (select != 4);
                System.out.println("Tekrar görüşmek üzere. ");
                break;
            } else {
                --right;
                if (right == 0) {
                    System.out.println("Hesabiniz bloke olmuştur. Lütfen banka ile iletişime geciniz");
                    break;
                }
                System.out.println("Hatali kullanici adi veya sifre. Tekrar deneyiniz.");
                System.out.println("Kalan hakkiniz : " + right);
            }
        }
    }
}
