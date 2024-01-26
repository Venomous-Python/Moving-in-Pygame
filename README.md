import pygame (All of this until line 10 is just setting up the screen and making everything run)

pygame.init()

SCREEN_WIDTH = 600
SCREEN_HEIGHT = 400

screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))

player = pygame.Rect((300, 250, 50, 50)) (This is telling Pygame to make a rectangle, you can change the measurements as it depends on you)

run = True
while run:

    screen.fill((R, G, B)) (This is just the colour of the screen, you need to add a number from 0 - 255 for it to work)

    pygame.draw.rect(screen, (255, 0, 0), player) (This displays the rectange on the screen)
        
    key = pygame.key.get_pressed() (if a is pressed player moves left left)
    if key[pygame.K_a] == True:
        player.move_ip(-1, 0)
        
    elif key[pygame.K_d] == True: (if d player moves right)
        player.move_ip(1, 0) 
    if key[pygame.K_w] == True: (if w player moves up)
        player.move_ip(0, -1)
    if key[pygame.K_s] == True: (if s player moves down)
        player.move_ip(0, 1)

    for event in pygame.event.get(): (This is just giving you the abililty to close the window when running)
        if event.type == pygame.QUIT:
            run = False

    pygame.display.update()

pygame.quit()
