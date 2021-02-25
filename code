org 100h


.data 
arr1 db 2d,2d,3d,8d
arr2 db 3d,5d,8d,0d
mergeArr db ?   



.code

MAIN Proc 

mov cl , 8
mov bx , offset arr1
mov si , offset mergeArr 



merge_NoDuplicate:
 
    mov al , [bx] 
    mov bp , offset mergeArr 
 
 check_forDuplicate:
       cmp al , [bp]
       je incIndex
       cmp bp , si
       je addElement
       inc bp
 jmp check_forDuplicate      
  


  addElement:
    mov [si] ,al
    inc si    

  incIndex:
    inc bx                                                
    dec cl   
    
jnz merge_NoDuplicate     
 
 
mov cl,8    
sort_outer_loop:   


  mov bx , offset mergeArr
  mov si , offset mergeArr 
  inc si
 sort_inner_loop:
  mov al , [bx]
  cmp al , [si]
 jb indexPlus
 
 swap:
  mov dl ,[si]
  mov [si] ,al
  mov [bx] ,dl

 indexPlus:
  inc bx
  inc si
  cmp si , bp
  jbe sort_inner_loop 
     
     
dec cl
jnz sort_outer_loop

 
 
mov bx , offset mergeArr
 print:   
 
    mov dl , [bx]
    add dl , 30h

    mov ah ,2h
    int 21h

    inc bx
    cmp bx , bp
 jbe print 

      
END MAIN 








