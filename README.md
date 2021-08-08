# RectToSQ
Given two dimensions, a positive integer length and a positive integer width. You will return a collection or a string (depending on the language; Shell bash, PowerShell, Pascal and Fortran return a string) with the size of each of the squares.  Examples in general form:  sqInRect(5, 3) should return [3, 2, 1, 1] sqInRect(3, 5) should return [3, 2, 1, 1]

Template

    # template
    # def recSquare(L, B):
    #     make an empty list numSquare
    #     make while loop condition L-B >= 1:
    #         new L = L - B
    #         numSquare.append(B)
    #     condition no longer true
    #     if L-B == 0: 
    #         return numSquare
    #     else:
    #         recSquare(B, L)
        
        
Code

    def sqInRect(l, b): #main function
        if l==b: #if length is equal to width to begin with it isnt a rectangle
            return None
        numsq=[]
        def sqAlgo(l , b): #algorithm
            while l>b: #while length is greater than width
                l= l-b #update length
                numsq.append(b)#add sqare with side width to list

            if l==b: # if l == b return after adding the last square 
                numsq.append(b)
                return numsq
            else: # the point of swap when b > l
                sqAlgo(b, l) #b becomes l, l becomes b
            return numsq
        return sqAlgo(l, b)    
        
 run
 
    print(sqInRect(30,50))
    print(sqInRect(8,6))
    print(sqInRect(30,5))
    print(sqInRect(3,50))
    print(sqInRect(340,50))
    print(sqInRect(30,560))
    
output

    [30, 20, 10, 10]
    [6, 2, 2, 2]
    [5, 5, 5, 5, 5, 5]
    [3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 2, 1, 1]
    [50, 50, 50, 50, 50, 50, 40, 10, 10, 10, 10]
    [30, 30, 30, 30, 30, 30, 30, 30, 30, 30, 30, 30, 30, 30, 30, 30, 30, 30, 20, 10, 10]
