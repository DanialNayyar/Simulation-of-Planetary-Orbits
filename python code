import pygame
import math

pygame.init()


width = 1900 
height = 1000
#0,0 is the top left hand corner,
#1800,0 is the top right hand corner
#0,1800 is the bottom left corner
#1800,1000 is the bottom right hand corner
win = pygame.display.set_mode((width,height))
pygame.display.set_caption(" Simulation of Planetary Orbits")


win_colour = (26,26,26)
grey = (153,153,153)
yellow = (255,255,0)
light_blue = (51,150,255)
red = (255,0,0)
brown = (150,75,0)
uranus_colour = (52,255,254)
dark_blue = (20,50,255)
light_brown = (179,138,139)
purple = (143,17,255)

r_scale = 5000000

AU = 14960e11
G = 6.67430e-11
AU_pixels = 100
scale_f = width/AU_pixels # = 
time_step = 3600*24

earth_d = 1


class Planet:
    AU = 14960e11
    G = 6.67430e-11
    AU_pixels = 100
    scale_f = width/AU_pixels
    time_step = 3600*24

    def __init__(self,x,y,r,colour,mass):# x,y = position, r = raidus, colour = colour, mass = mass
        self.x = x * Planet.scale_f
        self.y = y * Planet.scale_f
        self.r = r
        self.colour = colour
        self.mass = mass
        
        self.sun = False

        self.d_to_sun = 0

        self.orbit = [] # keeps track of all the points, the planet has travelled across to then be able to draw a circular orbit for it

        self.x_vel = 0 # velocity in x component  
        self.y_vel = 0 # velocity in y component

    def draw(self,win):
        x = self.x * self.scale_f + width / 2
        y = self.y * self.scale_f + height/ 2  
        pygame.draw.circle(win, self.colour,(x,y), self.r)






def main():
    run = True
    clockspeed = pygame.time.Clock()

    sun = Planet (0,0, (35), yellow, 2e30) # m = 2e30, colour = yellow
    sun.sun = True

    earth = Planet (-1*earth_d, 0, (8), light_blue, 6e24 ) #mass = 6e24, colour = Light Blue, 
    mars = Planet (-1.2*earth_d, 0, (8), red, 6.41941e23)
    mercury = Planet (-0.5*earth_d, 0, (6), grey, 3.302e23)
    jupiter = Planet (-1.4*earth_d, 0, (15), brown, 1.898e27)
    neptune = Planet (-1.9*earth_d, 0, (10), dark_blue, 1.0244e26)
    venus = Planet (-0.7*earth_d, 0, (9), light_brown, 4.8690e24)
    uranus = Planet (-2.2*earth_d, 0, (13), uranus_colour, 8.68e25)
    saturn = Planet (-1.7*earth_d, 0, (18), purple, 5.68e26)

    planets = [sun, mercury, venus, earth, mars, jupiter, saturn, uranus, neptune]


    while run == True:
        clockspeed.tick(60)
        win.fill(win_colour)
        

        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                run = False
        
        for planet in planets:
            planet.draw(win)

        pygame.display.update()

    pygame.quit()


main()
