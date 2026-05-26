# Módulo (función) para determinar la cantidad exacta a pedir
def calcular_cantidad_a_pedir(stock_actual, stock_minimo):
    if stock_actual < stock_minimo:
        return stock_minimo - stock_actual
    else:
        return 0

# Matriz con los datos de los artículos: [Código, Nombre, Stock Actual, Stock Mínimo]
inventario = [
    ["ART001", "Cuadernos", 12, 20],
    ["ART002", "Bolígrafos", 45, 30],
    ["ART003", "Marcadores", 5, 15],
    ["ART004", "Resmas de Papel", 8, 8],
    ["ART005", "Calculadoras", 2, 10]
]

# Procesamiento y salida del reporte de pedidos
print("=== LISTA DE PEDIDOS PARA REABASTECIMIENTO ===")
for articulo in inventario:
    nombre = articulo[1]
    stock_actual = articulo[2]
    stock_minimo = articulo[3]
    
    # Llamada al módulo lógico
    cantidad_pedir = calcular_cantidad_a_pedir(stock_actual, stock_minimo)
    
    # Imprime el nombre del artículo y la cantidad exacta solicitada
    print(f"Artículo: {nombre:<20} | Cantidad a pedir: {cantidad_pedir}")
