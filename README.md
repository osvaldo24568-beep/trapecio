from abc import ABC, abstractmethod

class Figura(ABC):
    @abstractmethod
    def calcular_perimetro(self) -> float:
        pass

    @abstractmethod
    def calcular_area(self) -> float:
        pass

    @abstractmethod
    def obtener_nombre(self) -> str:
        pass

class Trapecio(Figura):
    def __init__(self, base_mayor: float, base_menor: float, lado1: float, lado2: float, altura: float):
        self.base_mayor = base_mayor
        self.base_menor = base_menor
        self.lado1 = lado1
        self.lado2 = lado2
        self.altura = altura

    def calcular_perimetro(self) -> float:
        return self.base_mayor + self.base_menor + self.lado1 + self.lado2

    def calcular_area(self) -> float:
        return ((self.base_mayor + self.base_menor) / 2) * self.altura

    def obtener_nombre(self) -> str:
        return "Trapecio"

if __name__ == "__main__":
    tr = Trapecio(8, 5, 4, 4, 3)
    print(tr.obtener_nombre())
    print(f"Perímetro: {tr.calcular_perimetro():.2f}")
    print(f"Área: {tr.calcular_area():.2f}")
