# 2022/06/30 교내 알고리즘 대회

```java
package dapc;

import java.io.*;
import java.util.ArrayList;
import java.util.Scanner;
import java.util.StringTokenizer;

public class Main {
    public static void main(String[] args) throws IOException {

        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        StringTokenizer st = new StringTokenizer(br.readLine());
        int length = Integer.parseInt(st.nextToken());
        int bombCount = Integer.parseInt(st.nextToken());

        int[][] array = new int[length][length];

        for(int i = 0; i<bombCount; i++){
            StringTokenizer str = new StringTokenizer(br.readLine());
            int a = Integer.parseInt(str.nextToken());
            int b = Integer.parseInt(str.nextToken());
            
            if(array[a][b] != 9){
                array[a-1][b] ++;
                array[a-1][b+1]++;
                array[a][b+1]++;
                array[a+1][b+1]++;
                array[a+1][b]++;
                array[a+1][b-1]++;
                array[a][b-1]++;
                array[a-1][b-1]++;
            }

            array[a][b] = 9;
        }

        for(int i = 0; i<length;i++){
            for(int j = 0; j< length;j++){
                if(array[i][j]>9){
                    System.out.print(9+" ");
                } else {
                    System.out.print(array[i][j] + " ");
                }
            }
            System.out.println();
        }
//        ArrayList<Data> arrayList = new ArrayList();
//
//        Scanner scanner = new Scanner(System.in);
//        int count = scanner.nextInt();
//
//        for(int i = 0; i<count; i++){
//            int N = 0;
//            int M = 0;
//            int X = 0;
//            int D = 0;
//            for(int j = 0; j<4;j++){
//                int num = scanner.nextInt();
//
//                switch (j){
//                    case 0: {
//                        N = num;
//                        break;
//                    }
//                    case 2: {
//                        M = num;
//                        break;
//                    }
//                    case 3: {
//                        X = num;
//                        break;
//                    }
//                    case 4: {
//                        D = num;
//                        break;
//                    }
//                }
//
//                arrayList.add(new Data(N,M,X,D));
//            }
//        }
//
    }

}

class Data{
    int N;
    int M;
    int X;
    int D;

    public Data(int N, int M, int X, int D){
        this.N = N;
        this.M = M;
        this.X = X;
        this.D = D;
    }

    public int getN(){
        return N;
    }
    public void setN(int n) {
        N = n;
    }

    public int getM(){
        return M;
    }

    public void setM(int m) {
        M = m;
    }

    public int getX(){
        return X;
    }
    public void setX(int x) {
        X = x;
    }

    public int getD() {
        return D;
    }

    public void setD(int d) {
        D = d;
    }
}





//        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
//
//        StringTokenizer st = new StringTokenizer(br.readLine());
//        int length = Integer.parseInt(st.nextToken());
//        int bombCount = Integer.parseInt(st.nextToken());
//
//        length += 2;
//        int[][] array = new int[length][length];
//
//        for(int i = 0; i<bombCount; i++){
//            StringTokenizer str = new StringTokenizer(br.readLine());
//            int a = Integer.parseInt(str.nextToken());
//            int b = Integer.parseInt(str.nextToken());
//
//            if(array[a][b] < 9){
//                array[a-1][b] ++;
//                array[a-1][b+1]++;
//                array[a][b+1]++;
//                array[a+1][b+1]++;
//                array[a+1][b]++;
//                array[a+1][b-1]++;
//                array[a][b-1]++;
//                array[a-1][b-1]++;
//            }
//
//            array[a][b] = 9;
//        }
//
//        for(int i = 1; i<length-1;i++){
//            for(int j = 1; j< length-1;j++){
//                if(array[i][j]>9){
//                    System.out.print(9+" ");
//                } else {
//                    System.out.print(array[i][j] + " ");
//                }
//            }
//            System.out.println();
//        }




//        int answer = 0;
//
//        ArrayList canList = new ArrayList<Integer>();
//        ArrayList cannotList = new ArrayList<Integer>();
//        int canListCount = 1;
//        int cannotListCount = 1;
//
//        Scanner sc = new Scanner(System.in);
//
//        int studentTotal = sc.nextInt();
//        int tall = sc.nextInt();
//
//        for(int i = 0; i<studentTotal; i++){
//             int vs = sc.nextInt();
//             if(vs>tall){
//                 cannotList.add(vs);
//             }else {
//                 canList.add(vs);
//             }
//        }
//
//        for(int i = 1; i<=canList.size();i++){
//            canListCount *= i;
//        }
//
//        for(int i = 1; i<=cannotList.size();i++){
//            cannotListCount *= i;
//        }
//
//        answer = canListCount * cannotListCount;
//        System.out.println(answer);
```

- 2문제 시도 1문제 성공
- 3번째 문제는 하다가 말았음
- 앞으로 열심히 해야겠다고 느낌

```java
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        StringTokenizer st = new StringTokenizer(br.readLine());
        int length = Integer.parseInt(st.nextToken());
        int bombCount = Integer.parseInt(st.nextToken());

        int[][] array = new int[length][length];

        int[] dx = {-1, -1, -1, 0, 0, 1, 1, 1};
        int[] dy = {-1, 0, 1, -1, 1, -1, 0, 1};

        int nx, ny;

        for(int i = 0; i<bombCount; i++){
            StringTokenizer str = new StringTokenizer(br.readLine());
            int a = Integer.parseInt(str.nextToken());
            int b = Integer.parseInt(str.nextToken());
            a -= 1;
            b -= 1;

            for(int j = 0; j<8; j++){
                if(array[a][b] == 9) break;
                nx = dx[j] + a;
                ny = dy[j] + b;
                if(nx < 0 || nx >= length || ny < 0 || ny >= length) continue;
                array[nx][ny] += 1;
            }
            array[a][b] = 9;
        }

        for(int i = 0; i<length;i++){
            for(int j = 0; j< length;j++){
                if(array[i][j]>9){
                    System.out.print(9+" ");
                } else {
                    System.out.print(array[i][j] + " ");
                }
            }
            System.out.println();
        }
```

- 친구가 짜준 코드