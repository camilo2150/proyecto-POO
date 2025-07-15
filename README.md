
Clases Principales
Producto:
Representa un producto general del inventario con Clase base con atributos como código, nombre, precio, cantidad, unidad de medida y fechas

class Producto:
    def __init__(self, codigo:str, nombre: str, precio:float, cantidad:int,
                 unidad_medida:str, familia:str, ubicacion:str,
                 fecha_ingreso:date, fecha_vencimiento:Optional[date],
                 agotado:bool, stock_minimo: int):
        self.codigo = codigo
        self.nombre = nombre
        self.precio = precio

 
 Ingrediente (hereda de Producto):
Incluye proveedor y si es refrigerado.

class Ingrediente(Producto):
    def __init__(..., proveedor:str, es_refrigerado:bool ):
        super().__init__(...)
        self.proveedor = proveedor

 Movimiento:
Representa un registro de entrada o salida del inventario.

class Movimiento:
    def __init__(self, tipo: str, producto: Producto, cantidad:int,
                 fecha, usuario:str, motivo:str):
        self.es_refrigerado = es_refrigerado

Inventario
Conecta con la base de datos y gestiona los productos.

class Inventario:
    def __init__(self):
        self.conn = sqlite3.connect('inventario.db')
        self.cursor = self.conn.cursor()
        self.database()

    def database(self):
        self.cursor.execute('''
            CREATE TABLE IF NOT EXISTS BOD (
                codigo TEXT PRIMARY KEY,
                name TEXT,
                precio REAL,
                cantidad INTEGER,
                medida TEXT,
                fechaingreso TEXT
            )
        ''')
        self.conn.commit()












































 ![Diagrama UML](https://github.com/user-attachments/assets/060e29ff-ad26-45c1-a0b7-515846619d5c)
 ![Captura de pantalla 2025-06-18 120031](https://github.com/user-attachments/assets/59627228-a8a1-49df-abcb-739ab951322a)




