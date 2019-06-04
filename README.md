class House:
    def __init__(self):
      self.data =[
            "the house that Jack built",
            "the malt that lay in",
            "the rat that ate",
            "the cat that killed",
            "the dog that worried",
            "the cow with the crumpled horn that tossed",
            "the maiden all forlorn that milked",
            "the man all tattered and torn that kissed",
            "the judge all shaven and shorn that married",
            "the rooster that crowed in the morn that woke",
            "the farmer sowing his corn that kept",
            "the horse and the hound and the horn that belonged"
        ]

    def getdata(self):
        return self.data

    def parts(self, number):
        index = number - 1
        return self.getdata()[index::-1]

    def phrase(self, number):
        phrase = ""
        for line in self.parts(number):
            phrase += line + " "

        return phrase

    def line(self, number):
        print("This is %s" % self.phrase(number))

    def recite(self):
        for i in range(1, len(self.data())):
            self.line(i)
            
import random

class RandomHouse(House):
        def getdata(self):
          random.shuffle(self.data)
          return self.data

class EchoHouse (House):
  def phrase(self, number):
        phrase = ""
        for line in self.parts(number):
            phrase += line + " " + line + " "
        return phrase

class RandomEchoHouse(RandomHouse,EchoHouse):
  pass 

def dots():
  print('::::::::')

house = House()
randomHouse = RandomHouse()
echoHouse = EchoHouse()
randomechoHouse = RandomEchoHouse()

house.line(3)
dots()
randomHouse.line(3)
dots()
echoHouse.line(3)
dots()
randomechoHouse.line(3)
dots()
