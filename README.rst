#########################
Machine Learning Seminars
#########################

В папках voron1, voron2 находятся лекции к 1 и 2 семестру курса К.В.Воронцова по машинному обучению. Там же хранятся файлы вида notes_lec_x.txt - мои записи к соответствующей лекции.
В папке seminars находятся ноутбуки А.Гробового по этому же курсу. Ниже приведено их описание с моими замечаниями.


Осений семестр
==============


sem01 Вводный семинар
************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem1/main.ipynb>`_:
    - Теореотическая часть:
        - Общие идеи оптимизации, функции ошибок и тд.
    - Практическая часть:
        - При помощи sklearn показать пример Ирисов Фишера.
        - Понятие модели алгоритмов, алгоритм обучения, процесс оптимизации для конкретной задачи.
        - Переход от бинарной классификации к многоклассовой.
        - Переобучение. Борьба с переобучениям.
        - Немного о типах задач машинного обучения: прикладные и исследовательские
     - Замечания:
        - Y = reshape(-1), чтобы был столбец
        - сложение векторов размера (d,1) с (d,m) даст (d,m).
        - короткое закрашивание точек по классам через np.unique
        - удобное использование интерполяции и сразу же создание полинома
        - короткая запись матрицы ошибок всех моделей

sem02 Линейные методы классификации и регрессии: метод стохастического градиента
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem2/main.ipynb>`_:
    - Теореотическая часть:
        - Анализ стохастического градиента на сходимость.
        - Задача линейной регрессии, МНК в общем случае.
        - Постановка задачи линейной регрессии через правдоподобие, вероятностные предположения для данных и регуляризаторов.
    - Практическая часть:
        - Разбор домашнего задания.
        - Метод стохастического градиента на практике.
        - Использования torch framework для нахождения градиента сложной функции.
        - Вероятностная постановка задачи машинного обучения. Регуляризация l1, l2.
        - Анализ зависимости решения задачи оптимизации от параметра регуляризации.
        - Выбор параметра регуляризации при помощи LOO.
     - Замечания:
        - ввел generator, scheduler, optimizer
        - есть код для графиков обучения
        - пример реализации LOO для подбора коэффициента регуляризации

sem03 Нейронные сети: Autograd
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem3/main.ipynb>`_:
    - Теореотическая часть:
        - Автоматическое диференцирование.
    - Практическая часть:
        - Разбор домашнего задания.
        - Построение простой нейросетевой модели: многослойный персептрон.
        - Обучение персептрона на выборке MNIST.
        - Подбор гиперпараметров модели.
        - Прореживание сетей (без кода, только графики).
     - Замечания:
        - технический момент при добавлении прогнозов в многоклассовой классификации.
        - простой датасет для проверок алгоритмов - Fashion Mnist

sem04 Метрические методы классификации и регрессии
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem4/main.ipynb>`_:
    - Практическая часть:
        - Разбор домашнего задания.
        - Пример как можно отказаться от признаков в линейном классификаторе.
        - Метод ближайших соседей, анализ разного количества соседей.
        - Ядра в методе ближайших соседей.
        - Метод Парзеновского окна.
        - Метод потенциальных функций (реализация).
        - Отбор эталонных элементов, алгоритм STOLP.
        - Формула Надарая-Ватсона.
     - Замечания:
        - Реализация метода потенциальных функций 
        - Метод отбора эталонных «признаков» в методе потенциальных функций STOLP (я думаю там первая инициализация берется для простой плоскости с нормалью 1, -1.
        - удобный цикл ‘for i, (x, y) in enumerate(zip (X,Y)):’
        - короткая реализация подсчета отступов  (через pfm высчитываем margin для отбора эталонных объектов)
        - реализация формула Надарая-Ватсона    


sem05 Линейные методы классификации и регрессии: метод опорных векторов
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem5/main.ipynb>`_:
    - Практическая часть:
        - SVM для классификации.
        - Примеры использования ядер для SVM.
        - SVM для регрессии.
        - Генерация признаков на основе опорных элементов.
     - Замечания:
        - реализация SVC, отображение опорных объектов
        - пример того, что в случае концентрических окружностей линейный классификатор не то что плохо классифицирует, а вообще ломается
        - пример как построить ядро квадратичное,  которое уже разделит окружности (по свойствам отображения <uv>^2 из лекций)
        - приведен пример создания новых признаков для задачи классификации через расстояние до опорных векторов    

    
sem06 Многомерная линейная регрессия. Метод главных компонент
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem6/main.ipynb>`_:
    - Практическая часть:
        - Многомерная линейная регрессия.
        - Сингулярное разложение.
        - Регуляризация для многомерной регрессии: используя SVD.
        - Зависимость качества аппроксимации от числа обусловленности.
        - Метод главных компонент: визуализация MNIST.
        - Метод главных компонент: для изображений.
     - Замечания:
        - реализация svd через np с тонкостями насчет v,d
        - насчет плохих  собственных значений интересный момент, что они мешают предсказывать устойчиво вектор параметров, а при предсказывании у этого уже нет
        - показали, как l2 регуляризация в случае многомерной линейной регрессии повысила устойчивость к шуму.
        - примеры pca для анализа изображений
        - важно помнить, что если надо кучу псевдообратных матриц посчитать (при регуляризации, например), то проще  посчитать один раз svd. Но одна псевдообратная считается много меньше SVD.

sem07 Нелинейная регрессия. Обощенные линейные модели. Нестандартные функции потерь.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem7/main.ipynb>`_:
    - Практическая часть:
        - Нелинейная регрессия.
        - Сравнение градиентного спуска, метода Ньютона-Рафсона, метода Ньютона-Гаусса.
        - Обобщённые линейные модели: оптимальный размер выборки.
        - Функция потерь для задачи поиска близких предложений.
        - Визуализация сходимости метода Ньютона-Рафсона и стохастического градиента.
     - Замечания:
        - Ставим задачу восстановления функции из заданного семейства. Реализовали метод Ньютона-Рафсона и Гаусса-Рафсона.
        - пример применения экспоненциальности семейства распределений для определения размеров оптимальной выборки
        - пример нелинейной функции потерь при задачи построения эмбедингов.
        - визуализация методов оптимизации на 3д картинке     
    
sem08 Критерии выбора моделей и методы отбора признаков.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem8/main.ipynb>`_:
    - Практическая часть:
        - Оценка качества моделей: внешний и внутрений критерии.
        - Отбор признаков: полный перебор, алгоритм Add, алгоритм Add-Del.
        - Качество классификации: Precision, Recall.
        - Пример задачи information retrieval.
        - О составлении выборки для постановки задачи ML.
     - Замечания:
        - Поговорили про переобучение, про создание валидационных выборок.
        - Красивый отбор признаков по значению на валидации через itertools.product
        - Визуализация score по количеству отобранных признаков
        - Реализация add алгоритма 
        - Оффтоп про задачу создания выборки     


sem09 Логические методы классификации.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem9/main.ipynb>`_:
    - Практическая часть:
        - Логический классификатор: реализация.
        - Примеры задач для решения логичеким классификатором.
        - Критерии информативности.
        - Решающий список, простая реализация.
        - Решающее дерево.
        - Случайный лес.
     - Замечания:        
        - Реализация простого логического классификатора
        - Надо узнать, что делает * при передаче параметров
        - Реализация комитета и визуализация деревьев
        - Построили различные леса и поговорили про важность параметров.

sem10 Поиск ассоциативных правил.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem10/main.ipynb>`_:
    - Практическая часть:
        - Постановка задачи ассоциативных правил.
        - Синтетичекий пример.
        - Пример реальных данных из kaggle.
        - Алгоритм APriory.
        - Алгоритм FP-growth.
        - Обобщение для вещественных данных.
        - Обобщенные ассоциативные правила.
     - Замечания:        

    
sem11 Композиции классификаторов.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem11/main.ipynb>`_:
    - Практическая часть:
        - DummyEnsemble.
        - AdaBoost.
        - Градиентный бустинг, XGBoost.
        - Пример реальных данных из kaggle.
        - RandomForest.
        - Mixture Of Expert.
     - Замечания:        
        1) Реализация своего класса ансамблирования (для удобного использования в sklearn’e)
Важно иметь метод get_params, predict_proba
        - stratified kfold - выборки с сохранением % классов
Вспомнили, что в случайном лесе важно обеспечивать различность деревьев помимо бэггинга через выбор случайных подпространства
        - Идея смеси экспертов - вес модели зависит от некоторой уверенности в том, что объект принадлежит именно это модели (берется по факту выпуклая комбинация базовых решений функциями от х и каких-то параметров)
        - Фишка с ем алгоритмом

sem12 Композиции классификаторов (градиентный бустинг).
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem12/main.ipynb>`_:
    - Практическая часть:
        - ComBoost.
        - Gradient Boosting.
        - XGBoost.
        - CatBoost.
     - Замечания:  
        - Реализация comboost на базе sklearn опять
        - Запустили xgbr, lightgbm, catboost     
- Домашнее задание:
    - Реализовать комитетный бустинг для задачи регрессии.
    
sem13 Байесовская теория классификации.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem13/main.ipynb>`_:
    - Практическая часть:
        - Принцип максимума правдоподобия: визуализация.
        - Востановление плотности по империческим данным.
        - LOO для ввыбора ширины окна.
        - Наивный байесовский классификатор.
     - Замечания:        
        - Код для смесей
sem14 Методы кластеризации и обучение на неразмеченных данных.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem14/main.ipynb>`_:
    - Практическая часть:
        - Задача кластеризации.
        - Примеры кластеров.
        - K-means.
        - DBSCAN.
        - Иерархическая кластеризация.
        - Частичное обучение.
        - Self-training, 1970.
        - Неразмеченные данные в глубоком обучении.
     - Замечания: 
        - Показали, что есть очень сильная зависимость от метрики
        - Запуск kmeans с отображением центров класетров     

Весений семестр
===============


sem15 Глубокие Нейронные Сети. Сверточные Нейросети и Рекуррентные сети.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem15/main.ipynb>`_:
    - Практическая часть:
        - Сверточные нейронные сети.
        - Отслеживание обучения при помощи tensorboard.
        - Рекурентные нейронные сети.
        - Использование предобученных моделей.
        - Интерпретируемость ответов нейросети.
     - Замечания:
        - разбитие обучения на обучение по батчу, эпохе и эпохам
        - код для подсчета ошибки через батчи и домножение (можно with_no_grad добавить)
        - вывод промежуточных изображений cnn я пропускаю
        - пояснение применения функции callback: она на основе торча логирует и ошибки, и результаты моделей, можно даже сохранять веса 
        - tensor board (так и не научился открывать его в браузере) 
        - показали реализацию dataloader’a для задач с текстами
        - set_postfix для tqdm, yield
        - в lstm важно передать в формате seq_len , batch_size, emd_dim
        - важно иметь optimizer при обучении декодера и энкодера сразу для всех параметров.
        - введение ignore_index для корректного подсчета ошибок при пополнении размера матча фиктивными элементами
        - загрузили resnet, построили для нее препроцессор
        - библиотека lime для выявления важных признаков.
        - реализация простой seq2seq архитектуры через lstm 
        - (С токенизацией и прочим я решил не заморачиваться. Как буду писать проект или задание - открою и посмотрю).     
        
sem16 Нейронные сети. Автокодировщик. Transfer Learning. Генеративно-Состязательные сети.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem16/main.ipynb>`_:
    - Практическая часть:
        - Автокодировщик.
        - Линейный автокодировщик.
        - Автокодировщик на основе CNN.
        - Вариационный автокодировщик.
        - Перенос обучения с предварительно обученой модели.
        - Генеративно состязательные сети.
     - Замечания:  
        - определение preprocessing’a данных через transforms.Compose
        - реализация encoder decoder линейная, сверточная. Интересен декодировщик с параметрами сверток
        - реализация вариационного ae через нормальное распределение. Важен трюк с репараметризацией и torch.clamp для обработки граничных значений 
        - импорт resnet18 для классификации собак и кошек
        - реализация gun для mnist.      
        
sem17 Векторное представления текстов.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem17/main.ipynb>`_:
    - Практическая часть:
        - Пример классификации твитов.
        - Зачем нужна векторизация?
        - Токенизация текстов.
        - Word2Vec (на основе модели FastText).
        - FastText модель (сжатая до emb-dim=10 для легковесности).
        - Задачи для unsupervise training моделей векторизации.
     - Замечания:        
        - векторное представление текстов на базе fasttext.
        - Повторяем эту штуку на базе lstm, используя как эмбеддинг предложения последние состояния (h,c)
        - попробовали этап embedding не обучать, а взять готовый из fasttext
        - задачи с дообучением Bert     

sem18 Attention is all you need. Трансформеры.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem18/main.ipynb>`_:
    - Практическая часть:
        - Модель внимания в рекуррентных нейронных сетях.
        - Трансформеры.
        - T2T переводчик.
        - BPE токенизация.
        - BERT.
        - LaBSE.
     - Замечания:          
        - Строит простейшие трансформеры на базе lstm.      
        
sem19 Тематическое моделирование.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem19/main.ipynb>`_:
    - Практическая часть:
        - Модель LDA.
        - Модель PLSA (bigartm).
     - Замечания: 
        - Пример регулярного выражения для токенизатора
        - И куча всяких моделей из artm     

sem20 Пояснение к домашнему заданию.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem20/main.ipynb>`_:
    - Практическая часть:
        - Задачи из ДЗ.
     - Замечания:           

sem21 Задача ранжирования.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem21/main.ipynb>`_:
    - Практическая часть:
        - Базовые понятие.
        - Пример задачи ранжирования.
        - Пример рекомендательной системы.
        - Обучение поисковика на базе pyserini.
     - Замечания:           
        
sem22 Рекомендательные системы.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem22/main.ipynb>`_:
    - Практическая часть:
        - Константная модель.
        - Кореляционная система.
        - SLIM.
        - SVD.
     - Замечания:           


sem23 Временные ряды.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem23/main.ipynb>`_:
    - Практическая часть:
        - Авторегрессионая модель.
        - Экспоненциальное сглаживание.
        - Кластерный анализ временных рядов.
     - Замечания:           
        - интересно, что в авторегрессионной модели если взять слишком большую длину интервала и в нее попадет какой-то период, то у нас появится мультиколлинеарность
        - экспоненциальное среднее не работает для предсказания на 4 недели вперед             
sem24 Онлайновое обучение.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem24/main.ipynb>`_:
    - Практическая часть:
     - Замечания:       
    
    
sem25 Обучение с подкреплением.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem25/main.ipynb>`_:
    - Практическая часть:
        - Стационарный многорукий бандин.
        - Нестационарный многорукий бандин.
        - Задача о заплыве.
     - Замечания:     
        - Реализовали простые стратегии для стационарной среды
        - Игра «плавать по реке» -  простейшая динамическая среда
     
        
sem26 Активное обучение.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem26/main.ipynb>`_:
    - Практическая часть:
        - Активное обучение со случайным добавляющим элементом.
        - Активное обучение с добавлением элемента с максимальной дисперсией.
     - Замечания:  
        - Реализация простейшего активного обучения на базе искусственных данных (синусоида)
        - Красивая визуализация сходимости регрессора в виде гифки.
        - Реализация активного обучения на основе максимальной дисперсии от гауссовского процесса.     
        
sem27 Заключительное занятие.
*******************************************************************************
- `Семинар <https://github.com/andriygav/MachineLearningSeminars/blob/master/sem27/main.ipynb>`_:
    - Теоретическая часть:
        - Разбор Posterior Sampling
     - Замечания:                
         - Подход с апостериорным распределением в задаче предсказания поведения среды. Там просто строится матрица дирихле для предсказания нового состояния и матрица гамма-нормальная для предсказания выигрыша. На их основе выбирается действие (путем семплирования), а затем в зависимости от результата по формулам для сопряженных распределений пересчитываются параметры.
