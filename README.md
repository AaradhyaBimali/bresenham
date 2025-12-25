# bresenham
import pygame
import sys

# Initialize Pygame
pygame.init()

# Set up the display
WIDTH, HEIGHT = 800, 600
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Bresenham Algorithm") #set exe header

# Colors
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)

def bresen(x1,y1,x2,y2):
    dx=x2-x1
    dy=y2-y1
    if(x2>x1):
        lx=1
    else:
        lx=-1
    if(y2>y1):
        ly=1
    else:
        ly=-1
    k=0
    if (dx>dy):
        P=2*dy-dx
        while(k<dx):
            
            if (P<0):
                x1=x1+lx
                y1=y1
                P=P+2*dy
                
                screen.set_at((x1,y1), WHITE)
            else:
                x1=x1+lx
                y1=y1+ly
                P=P+2*(dy-dx)
                screen.set_at((x1,y1), WHITE)
            k=k+1
    else:
        P=2*dx-dy
        while(k<dy):
            screen.set_at((x1,y1), WHITE)
            
            if (P<0):
                x1=x1
                y1=y1+ly
                P=P+2*dx
            else:
                x1=x1+lx
                y1=y1+ly
                P=P+2*(dx-dy)
            k=k+1
                

def main():
    while True:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()

        # Clear the screen
        screen.fill(BLACK)
        bresen(100,200,200,70)
        
# Update the display
        pygame.display.flip()


if __name__ == "__main__":
    main()
        
        
        
