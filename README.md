
 Estructura de clases
Las clases principales del sistema son:
🔹 Clase Producto
Representa productos generales en el inventario. Ejemplo de constructor:

class Producto:
    def __init__(self, codigo:str, nombre: str, precio:float, cantidad:int, unidad_medida:str, familia:str, ubicacion:str, fecha_ingreso:date, fecha_vencimiento:Optional[date], agotado:bool, stock_minimo: int):
        self.codigo = codigo
        self.nombre = nombre
        self.precio = precio
        ...

🔹 Clase Ingrediente (hereda de Producto)
Agrega atributos como proveedor y si es refrigerado:

class Ingrediente(Producto):
    def __init__(..., proveedor:str, es_refrigerado:bool ):
        super().__init__(...)
        self.proveedor = proveedor
        self.es_refrigerado = es_refrigerado

🔹 Clase Movimiento
Representa una entrada o salida del inventario. Planeada para registrar qué, cuándo, cuánto y por qué:

class Movimiento:
    def __init__(self, tipo: str, producto: Producto, cantidad:int, fecha, usuario:str, motivo:str):
        ...

🔹 Clase Inventario
Gestiona la conexión con SQLite y el manejo de productos:

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



https://www.mermaidchart.com/app/projects/2d4cdfe7-5494-41d2-a8e1-4a7d4efd9384/diagrams/2744b662-8537-4757-92df-63ba8fc17ee7/share/invite/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJkb2N1bWVudElEIjoiMjc0NGI2NjItODUzNy00NzU3LTkyZGYtNjNiYThmYzE3ZWU3IiwiYWNjZXNzIjoiRWRpdCIsImlhdCI6MTc1MjU0NDkxMn0.Yqxpbc7hGZXB0JvD1U3v6GfSfsQSBawdO6NsPlS8528 
