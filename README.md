
Clases Principales
Producto:
Representa un producto general del inventario

class Producto:
    def __init__(self, codigo:str, nombre: str, precio:float, cantidad:int,
                 unidad_medida:str, familia:str, ubicacion:str,
                 fecha_ingreso:date, fecha_vencimiento:Optional[date],
                 agotado:bool, stock_minimo: int):
        self.codigo = codigo
        self.nombre = nombre
        self.precio = precio
        ...


























 ![Diagrama UML](https://github.com/user-attachments/assets/060e29ff-ad26-45c1-a0b7-515846619d5c)
 ![Captura de pantalla 2025-06-18 120031](https://github.com/user-attachments/assets/59627228-a8a1-49df-abcb-739ab951322a)




