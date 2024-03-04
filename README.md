import cv2
cap = cv2.VideoCapture(0)
fourcc = cv2.VideoWriter_fourcc(*'XVID')
out = cv2.VideoWriter('kamalelfar.avi', fourcc, 30.0, (640, 480))

while( True): 
    ret,frame=cap.read()
    
    if not ret:
        
        break
    
    flipped = cv2.flip(frame, 1)
    
    out.write(flipped)
            
    cv2.imshow('flippedframe',flipped)
        
    if cv2.waitKey(1)== ord('q'):
        break
            

cap.release()  # close the camera after closing the window
out.release()
cv2.destroyAllWindows()
