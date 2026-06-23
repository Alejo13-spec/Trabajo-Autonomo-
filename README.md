# Trabajo-Autonomo-

Interfaz Snake

import sys
import pygame

HEIGHT = 800
WIDTH = 800
BLACK = (0, 0, 0)
RED = (225, 0, 122)
PURPLE = (100, 0, 255)
YELLOW = (255, 236, 0)
GREEN = (43, 159, 3)
GRID_SIZE = 20


def draw_grid(window):
    window.fill(GREEN)
    x = 0
    y = 0
    for i in range(WIDTH):
        x += GRID_SIZE
        y += GRID_SIZE
        
        
        pygame.draw.line(window, BLACK, (x, 0), (x, WIDTH))
        pygame.draw.line(window, BLACK, (0, y), (HEIGHT, y))

def main():
    pygame.init()
    window = pygame.display.set_mode((HEIGHT, WIDTH))
    pygame.display.set_caption("Snake Game")
    
    clock = pygame.time.Clock()
    
    game_font = pygame.font.SysFont("Helvetica", 28)
    
    while True:
        
        clock.tick(11)
        
        for event in pygame.event.get():
            
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()
                
            draw_grid(window)  
            
            score = game_font.render("Score", True, BLACK)
            window.blit(score, (5, 0))
            best_score = game_font.render("Best score", True, BLACK)
            window.blit(best_score, (5, 30))
            
            pygame.display.update()
    
    
    
    
    
main()





