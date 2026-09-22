# OOP2026
### Homework1
```java

public class Homework1 {

	public static void main(String[] args) {
		int i, j;
        for (i = 0; i < 10; i++) {
            for (j = 0; j <= i; j++) {
                System.out.print("#");
            }
            System.out.println();
        }
        
        System.out.println();

        for (i = 0; i < 10; i++) {
            for (j = 0; j < 10 - i; j++) {
                System.out.print("#");
            }
            System.out.println();
        }

        for (i = 0; i < 10; i++) {
            for (j = 0; j < 9 - i; j++) {
                System.out.print(" ");
            }
            for (j = 0; j <= i; j++) {
                System.out.print("#");
            }
            System.out.println();
        }

        System.out.println();
        
        for (i = 0; i < 10; i++) {
            for (j = 0; j < i; j++) {
                System.out.print(" ");
            }
            for (j = 0; j < 10 - i; j++) {
                System.out.print("#");
            }
            System.out.println();
        }

	}

}


```
![Alt homework11](./images/hw1.jpg)

### Homework2
```java
public class Homework2 {

	public static void main(String[] args) {
		int a = 0;
		int b = 1;
		
		for(int i = 1; i<=20; i++) {
			System.out.print(a + " ");
			
			int next = a + b;
			a = b;
			b = next;
		}

	}

}
```
![Alt homework11](./images/hw2.jpg)

### Homework3
```java

public class Homework3 {

	public static void main(String[] args) {
		
		int a=1;
		int b=2;
		
		for(int i=1; i<=20; i++) {
			double ratio = (double) b / a;
			System.out.println(b + " / "+a+" = "+ratio);
			
			int next = a + b;
			a = b;
			b = next;
		}
	}

}

```
![Alt homework11](./images/hw3.jpg)

### Homework4
```java

public class Homework4 {

	public static void main(String[] args) {
		int i;
		int j;
		
		for(j = 1; j <= 9; j++) {
			for(i = 1; i <= 9; i++) {
				System.out.println(i+ "*" + j + "=" + (i*j)+ "\t");
			}
			System.out.println();
		}

	}

}

```
![Alt homework11](./images/hw4.jpg)


### Homework5
```java

public class Homework5{
public static double Gregory_Leibniz(int terms) {
        double pi = 0;

        for (int k = 0; k < terms; k++) {
            double sign;
            if (k % 2 == 0) {
                sign = 1.0; //짝
            } else {
                sign = -1.0; //홀
            }
            double term = sign * 4.0 / (2 * k + 1);
            pi += term;
        }

        return pi;
    }

    public static double Madhava(int terms) {
        double sum = 0;

        for (int k = 0; k < terms; k++) {
            double term = Math.pow(-3.0, -k) / (2 * k + 1); //홀일 때 음수, 짝일 때 양수
            sum += term;
        }
        return Math.sqrt(12.0) * sum;
    }
//
public class madhava {

	public static void main(String[] args) {
		int i,n=100,sign=1;
		double sum=0;
		for(i=0;i<n;i++) {
			sum += sign*1./((2.*i+1.)*Math.pow(3., i));
			sign *=-1;
		}
System.out.println(sum*Math.sqrt(12));
	}

} madahava부분 수정 필요

    public static void main(String[] args) {
        int glTerms = 1000000;
        int madhavaTerms = 20;

        System.out.println("자바 기본 Math.PI 값: " + Math.PI);
        double glResult = Gregory_Leibniz(glTerms);
        System.out.println("그레고리 라이프니츠 결과 : " + glResult); //100만번 반복
        double madhavaResult = Madhava(madhavaTerms);
        System.out.println("마다바 결과 : " + madhavaResult); //20번 반복
    }
}
```
![Alt homework11](./images/hw5.jpg)


### Homework6
```java
public class Binomial {
	public static void main(String[] args) {
	int n = 7;
    int binomial[][] = new int[n][];

    for (int i = 0; i < n; i++) {
        binomial[i] = new int[i + 1];
        
        for (int j = 0; j <= i; j++) {
            if (j == 0 || j == i) {
                binomial[i][j] = 1;
            } else {
                binomial[i][j] = binomial[i - 1][j - 1] + binomial[i - 1][j];
            }
        }
    }
    for (int i = 0; i < n; i++) {
        for (int j = 0; j <= i; j++) {
            System.out.print(binomial[i][j] + " ");
        }
        System.out.println();
    }
}
}
```

![Alt homework11](./images/hw6.jpg)

### Homework7
```java
public class Sorting {
    public static void main(String[] args) {
    	
        int data[] = new int[20];

        for(int i = 0; i < 20; i++) {
            data[i] = (int)(Math.random() * 100);
        }
        for(int i = 0; i < data.length - 1; i++) {
            int minIdx = i;
            
            for(int j = i + 1; j < data.length; j++) {
                if(data[j] < data[minIdx]) {
                    minIdx = j;
                }
            }
            
            int temp = data[i];
            data[i] = data[minIdx];
            data[minIdx] = temp;
        }

        for(int i = 0; i < 20; i++) {
            System.out.println(data[i]);
        }
    }
}
```
![Alt homework11](./images/hw7.jpg)

### Homework8
```java
public class Math_random {

	public static void main(String[] args) {

		        int score[][] = new int[30][6];

		        for (int i = 0; i < 30; i++) {
		            score[i][0] = i + 1;

		            int sum = 0;
		            for (int j = 1; j <= 4; j++) {
		                score[i][j] = (int)(Math.random() * 101);
		                sum += score[i][j];
		            }
		            score[i][5] = sum;
		        }
		        for (int i = 0; i < 30; i++) {
		            for (int j = 0; j < 6; j++) {
		                System.out.printf("%4d", score[i][j]);
		            }
		            System.out.println();
		        }
		    }
	}
```
![Alt homework11](./images/hw8.jpg)

