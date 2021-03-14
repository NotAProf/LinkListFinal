# LinkListFinal
 Assignment 1

public class LinkedListInteger {

	int number;

	public LinkedListInteger(final String number) throws Exception {
		try {
			this.number = Integer.parseInt(number);
		} catch (Exception e) {
			throw new Exception("Invalid input");
		}
	}

	public LinkedListInteger(final int number) {
		this.number = number;
	}

	public Integer getNumber() {
		return number;
	}

	public void reverseNumber() {
		String stringNumber = String.valueOf(number);
		String reversedNumberString = "";
		for (int i = stringNumber.length() - 1; i >= 0; i--) {
			reversedNumberString += stringNumber.charAt(i);
		}
		number = Integer.parseInt(reversedNumberString);
	}

	@Override
	public String toString() {
		return "Linked List Integer : " + this.number;
	}

	public Integer add(LinkedListInteger inputNumber) {
		return this.number + inputNumber.getNumber();
	}

	public Integer subtract(LinkedListInteger inputNumber) {
		return this.number - inputNumber.getNumber();
	}

	public Integer compareTo(LinkedListInteger inputNumber) {
		return this.number - inputNumber.getNumber();
	}

	public static void main(String[] args) {
		LinkedListInteger linkedListInteger1 = new LinkedListInteger(6);
		LinkedListInteger linkedListInteger2 = null;
		try {
			linkedListInteger2 = new LinkedListInteger("12");
		} catch (Exception e) {
			System.out.println(e.getMessage());
		}

		// adding two integers 6+12
		System.out.println(linkedListInteger1.add(linkedListInteger2));

		// reverse linkedListInteger2 to 21
		linkedListInteger2.reverseNumber();

		// add again 6+21
		System.out.println(linkedListInteger1.add(linkedListInteger2));

		// subtract the two numbers 6-21
		System.out.println(linkedListInteger1.subtract(linkedListInteger2));

		LinkedListInteger linkedListInteger3 = null;
		;
		try {
			linkedListInteger3 = new LinkedListInteger("-12");
		} catch (Exception e) {
			System.out.println(e.getMessage());
		}
		// subtract the two numbers -12-21
		System.out.println(linkedListInteger3.subtract(linkedListInteger2));

		LinkedListInteger linkedListInteger4 = null;
		;
		try {
			linkedListInteger4 = new LinkedListInteger("sdf25");
		} catch (Exception e) {
			System.out.println(e.getMessage());
		}

	}
}
