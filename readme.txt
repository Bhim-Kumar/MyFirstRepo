public class CheckingAccount {
    private double balance;

    public CheckingAccount(double initialBalance) {
        this.balance = initialBalance;
    }

    public void deposit(double amount) {
        balance += amount;
    }

    public boolean withdraw(double amount) {
        if (balance >= amount) {
            balance -= amount;
            return true;
        } else {
            return false;
        }
    }

    public double getBalance() {
        return balance;
    }
}

public class DebitCard {
    private CheckingAccount account;

    public DebitCard(CheckingAccount account) {
        this.account = account;
    }

    public void makePurchase(double amount) {
        if (account.withdraw(amount)) {
            System.out.println("Transaction successful. Remaining balance: " + account.getBalance());
        } else {
            System.out.println("Transaction failed. Insufficient balance.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        // Assuming Michael and Joseph have $100 in their account initially
        CheckingAccount account = new CheckingAccount(100);

        DebitCard michaelCard = new DebitCard(account);
        DebitCard josephCard = new DebitCard(account);

        // Michael tries to purchase an item worth $70
        michaelCard.makePurchase(70);

        // Joseph tries to purchase an item worth $50
        josephCard.makePurchase(50);

        // Joseph tries to purchase an item worth $100, which exceeds their balance
        josephCard.makePurchase(100);
    }
}
