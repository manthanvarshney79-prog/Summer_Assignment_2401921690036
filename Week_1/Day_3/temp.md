1. Matrix Diagonal Sum :-

 
 int diagonalSum(int** mat, int matSize, int* matColSize) {
    int total=0;
    for (int i=0;i<matSize;i++) {
        total+=mat[i][i];
    }
    for (int i=0;i<matSize;i++) {
        if (i!=matSize-i-1) {
            total+=mat[i][matSize-i-1];
        }
    }
    return total;
}



2. Reshape the Matrix :-

int** matrixReshape(int** mat, int m, int* n,int r, int c,int* returnSize,int** returnColumnSizes) {

    if (m*n[0]!=r*c) {
        *returnSize =m;
        *returnColumnSizes =n;
        return mat;
    }
    int** ans = malloc(r * sizeof(int*));
    *returnColumnSizes = malloc(r * sizeof(int));
    for (int i = 0; i < r; i++) {
        ans[i] = malloc(c * sizeof(int));
        (*returnColumnSizes)[i] = c;
    }
    for (int i = 0; i < m * n[0]; i++) {
        ans[i / c][i % c] = mat[i / n[0]][i % n[0]];
    }
    *returnSize = r;
    return ans;
}




3. Spiral Matrix :-

int* spiralOrder(int** matrix, int matrixSize, int* matrixColSize, int* returnSize) {
    int rows=matrixSize;
    int cols=matrixColSize[0];
    int* ans=malloc(rows*cols*sizeof(int));
    int top=0; int bottom=rows-1; int left=0;
    int right=cols-1; int index=0;
    while (top<=bottom && left <= right) {
        for (int i = left; i <= right; i++)
            ans[index++] = matrix[top][i];
        top++;
        for (int i = top; i <= bottom; i++)
            ans[index++] = matrix[i][right];
        right--;
        for (int i = right; i >= left && top <= bottom; i--)
            ans[index++] = matrix[bottom][i];
        bottom--;
        for (int i = bottom; i >= top && left <= right; i--)
            ans[index++] = matrix[i][left];
        left++;
    }
    *returnSize = index;
    return ans;
}


