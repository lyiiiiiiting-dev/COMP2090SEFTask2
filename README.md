# COMP2090SEFTask2
COMPTask2--Heap 
def heapify(arr, n, i):
    largest = i #Initialize largest as root
    left = 2 * i + 1 #Left child index
    right = 2 * i + 2 #Right child index

    #Find the largest element among root, left and right
    if left < n and arr[left] > arr[largest]:
        largest = left
    if right < n and arr[right] > arr[largest]:
        largest = right

    #Swap and continue heapifying if needed
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)
def heap_sort(arr):
    n = len(arr)
    #Build max-heap
    for i in range(n//2 - 1, -1, -1):
        heapify(arr, n, i)
    #Extract elements one by one
    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]
        heapify(arr, i, 0)
arr = [4, 10, 3, 5, 1]
heap_sort(arr)
print("Sorted array:", arr)
    
