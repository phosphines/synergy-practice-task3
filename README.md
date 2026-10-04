def sum_negatives_between_extrema(arr):
    if not arr or len(arr) < 3:
        return 0
        
    # Находим индексы минимального и максимального элементов
    min_idx = arr.index(min(arr))
    max_idx = arr.index(max(arr))
    
    # Определяем границы среза (не включая сами экстремумы)
    start = min(min_idx, max_idx) + 1
    end = max(min_idx, max_idx)
    
    # Считаем сумму отрицательных элементов в этом промежутке
    result_sum = sum(x for x in arr[start:end] if x < 0)
    return result_sum

# Пример тестирования алгоритма
if __name__ == "__main__":
    # Тестовый массив
    test_array = [4, -2, 10, -5, -3, -1, -8, 12, -4, 1]
    # Экстремумы здесь: min = -8 (индекс 6), max = 12 (индекс 7)
    # Между ними элементов нет, проверим другой вариант:
    
    another_array = [12, -3, -5, 2, -1, -8, 4] 
    # max = 12 (idx 0), min = -8 (idx 5)
    # Между ними: -3, -5, 2, -1. Отрицательные: -3, -5, -1. Сумма = -9
    
    print(f"Массив: {another_array}")
    print(f"Сумма отрицательных между min и max: {sum_negatives_between_extrema(another_array)}")
