FUNCTION multiply(matrixA, matrixB):

    BEGIN
    // Get dimensions
    rowsA = length of matrixA
    colsA = length of matrixA[0]
    rowsB = length of matrixB
    colsB = length of matrixB[0]

    // Validate if multiplication is possible
    IF colsA is NOT equal to rowsB THEN
        THROW Error "Dimension mismatch"
    END IF

    // Initialize the result matrix with zeros
    result = new 2D array with dimensions [rowsA][colsB]

    // Perform multiplication
    FOR i FROM 0 TO rowsA - 1:            // Iterate through rows of A
        FOR j FROM 0 TO colsB - 1:        // Iterate through columns of B
            FOR k FROM 0 TO colsA - 1:    // The common dimension
                // Dot product calculation
                result[i][j] = result[i][j] + (matrixA[i][k] * matrixB[k][j])
            END FOR
        END FOR
    END FOR

    RETURN result
END FUNCTION
