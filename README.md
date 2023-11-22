# Сегментация

## Датасет
[Датасет](https://drive.google.com/file/d/1PwK2oz_NbJU0NsT42Wr_Yv6rcZcJa5Uc/view?usp=sharing) представляет из себя набор подводных аннотированных снимков(исходные изображения - dataset/images, аннотации - dataset/masks), всего 1525 изображений и 8 категорий объектов:  
![image](https://github.com/compfee/CV_2023_lab5/assets/55783463/32eed333-d053-4378-a459-2ee1882ddd7a)

## Описание задачи
Язык программирования - Python  
Разрешено использовать любую библиотеку для машинного обучения (PyTorch, TensorFlow, Keras и др.)  
Необходимо создать модель для сегментации изображений с определением класса выделенной области  
Измерить время работы модели на тестовом датасете и посчитать необходимые метрики  
## Ограничения
Запрещено использование готовых архитектур "из коробки" одной строчкой. В коде должны быть прописаны слои вашей модели
## Метрики
Метрики оценки качества сегментации:  
IoU:  
![image](https://github.com/compfee/CV_2023_lab5/assets/55783463/b78b3cdc-4b02-48dd-a474-c8ec7845f5d2)  
​Per-class IoU:  
IoU по каждому из 8 классов  
Per-pixel accuracy:  
![image](https://github.com/compfee/CV_2023_lab5/assets/55783463/4093f270-9ca5-4fc8-a7de-10c93e1c44dd)  
 

## Решение
* Архитектура `U-net-like`, оптимизатор - `Adam`, loss - `sparse_categorical_crossentropy`, batch_size = `16`, learning_rate = `1e-4`, количество эпох = `12`, 

![image](https://github.com/ogalay/CV_2023_lab5/assets/43163344/f66cf7f2-ff4d-478e-b1b2-abbbbd0cd04b)

Результаты в процессе обучения

* Эпоха 1  

![image](https://github.com/ogalay/CV_2023_lab5/assets/43163344/a1739331-5cf0-485e-8af7-111a4359425e)

* Эпоха 6

![image](https://github.com/ogalay/CV_2023_lab5/assets/43163344/7977038e-6d5d-4ce4-87b0-38adb1d986ed)

* Эпоха 11

![image](https://github.com/ogalay/CV_2023_lab5/assets/43163344/dc2c8251-779f-476c-bba3-3d2f35b2954b)


## Полученные метрики на тестовом датасете
* Pixel Accuracy - `0.65`
* IoU - `0.24`
* Channel IoU - `[0.75, 0.02, 0.03, 0.001, 0.005, 0.42, 0.21, 0.48`


