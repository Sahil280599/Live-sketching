import cv2
# defining function of sketch
def sketch(image):
    # so when we convert the image color to grey scale so it create a blur image 
 
    img_gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
    
    # so to remove that we use GaussianBlur to remove that noise part
    img_gray_blur = cv2.GaussianBlur(img_gray, (5,5), 0)
    
    # so now to extract the edges
    canny_edges = cv2.Canny(img_gray_blur, 20, 50)
    
    # so after we get the clean pixel image we will binarize it 
    ret, mask = cv2.threshold(canny_edges, 70, 255, cv2.THRESH_BINARY_INV)
    return mask

# we put 0 to trigger webcam (# we can put image also)

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    cv2.imshow('Our Live Sketcher', sketch(frame))
    if cv2.waitKey(1) == 13: # so the wait key is at what time we have to use this program 13 is a enter key 
        break
        
# closing windows
cap.release()
cv2.destroyAllWindows()
