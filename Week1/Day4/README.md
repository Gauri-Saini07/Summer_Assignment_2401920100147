Day_4 work
1) Matrix Diagonal Sum
class Solution {
    public int diagonalSum(int[][] mat) {
        //matrix sum
        int sum=0;
        int n=mat.length;
        for(int i=0;i<n;i++){
            sum=sum+mat[i][i];
            sum=sum+mat[i][n-i-1];
        }
        if(n%2!=0){
            sum=sum-mat[n/2][n/2];
        }
        return sum;
    }
}

2) Reshape the matrix
 class Solution {
    public int[][] matrixReshape(int[][] mat, int r, int c) {
       // reshape the  matrix
        int m=mat.length;
        int n=mat[0].length;
        if(r*c!=m*n){
            return mat;
        }
        int res[][]=new int[r][c];
        for(int i =0;i<r*c;i++){
            res[i/c][i%c]=mat[i/n][i%n];
        }
        return res;

    }
}

3) Spiral Matrix
 class Solution {
    public List<Integer> spiralOrder(int[][] matrix) {
        //spiral matrix
        List<Integer> result = new ArrayList<>();
int m = matrix.length;
int n = matrix[0].length;

int srow = 0, scol = 0, erow = m - 1, ecol = n - 1;

while (srow <= erow && scol <= ecol) {
   for (int j = scol; j <= ecol; j++) {
        result.add(matrix[srow][j]);
    }
    for (int i = srow + 1; i <= erow; i++) {
        result.add(matrix[i][ecol]);
    }
    for (int j = ecol - 1; j >= scol; j--) {
        if (srow == erow) break; 
        result.add(matrix[erow][j]);
    }
    for (int i = erow - 1; i >= srow + 1; i--) {
        if (scol == ecol) break; 
        result.add(matrix[i][scol]);
    }
    srow++;
    erow--;
    scol++;
    ecol--;
}

return result;
}} 

