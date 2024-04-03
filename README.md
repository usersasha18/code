# code

```python

import pygame
from random import randint
pygame.init()

clock = pygame.time.Clock()
BACK = (255,255,255)
BLACK = (0,0,0)
LIGH_BLUE = (161,123,228)
window = pygame.display.set_mode((500,500))
window.fill(BACK)

class TextArea():
    def __init__(self, x=0, y=0, width=10, heihgt=10, color=None):
        self.rect = pygame.Rect(x, y, width, heihgt)
        self.fill_color = color


    def set_text(self, text, tsize=12,text_color=BACK):
        self.text = text
        self.image = pygame.font.Font(None,tsize).render(text, True,text_color)

    def draw(self, shift_x=0, shift_y=0):
        pygame.draw.rect(window, self.fill_color, self.rect)
        window.blit(self.image, (self.rect.x + shift_x, self.rect.y + shift_y))

quest_card = TextArea(120,100,290,70, LIGH_BLUE)
quest_card.set_text('Вопрос', 75)

ans_card = TextArea(120,240,290,700, LIGH_BLUE)
ans_card.set_text('Ответ', 75)

while 1:
    pygame.display.update()
    for event in pygame.event.get():
        if event.type == pygame.KEYDOWN:
            if event.key == pygame.K_q:
                num = randint(1,3)
                if num == 1:
                    quest_card.set_text('Арсений лох?', 35)
                if num == 2:
                    quest_card.set_text('арсений ты попу помыл?', 35)
                if num == 3:
                    quest_card.set_text('арсений супер пупер игрок в доту 2?', 35)

            if event.key == pygame.K_a:
                num = randint(1,3)
                if num == 1:
                    ans_card.set_text('Да', 35)
                if num == 2:
                    ans_card.set_text('кнш', 35)
                if num == 3:
                    ans_card.set_text('ДААААААААААААААААААААААААААААААААААААААААААААААААААААААААААААААААА', 35)
            


    quest_card.draw(10,10)
    ans_card.draw(10,10)
    clock.tick(40)
```












