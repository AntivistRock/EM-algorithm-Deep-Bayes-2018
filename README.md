# EM algorithm for the investigation

> ### Предыстория 
> Этот ноутбук является решением интересной задачи с [DeepBayes 2018](https://deepbayes.ru/2018/), куда она попала
> из [одной из лабораторных работ](https://cw.fel.cvut.cz/old/courses/ae4b33rpz/labs/12_em/start) курса Pattern Recognition and Machine Learning Чешского Технического Университета.
> В свою очередь я о ней узнал, как об одном из ДЗ [курса Тинькофф по глубокому обучению](https://fintech.tinkoff.ru/study/generation/dl/), когда проходил его.  
> У нас не было лекции о ЕМ алгоритме или разбора этой задачи, вдобавок у меня не хватило времени и знания математической статистики, чтобы сдать работу вовремя. И когда я вновь вернулся к ней, она все еще оставалась интересной для меня, но теперь я не мог рассчитывать на помощь преподавателей.

### Условие

Есть  **K**  изображений, на которых изображен один из организаторов DeepBayes, но все из них были повреждены следующим процессом: есть фиксированное черно-белое изображение-фон  **B**  (размера  W×H ), в каждом изоражении лицо  **F**  (размера  *w×H* ) помещается в случайное место на фоне (для каждого изображения выбирается горизонтальный сдвиг  *dk* ; априорные вероятности каждого сдвига обучаемы). Помимо этого, ко всем изображениям подмешивается белый шум (независимо ко всем пикселям) со средним 0 и дисперсией  **s2**.

Задача — восстановить лицо. Формально, нужно найти такую матрицу, что правдоподобие сгенерированных изображений максимально.

### Комментарии к решению

* Вы можете просмотреть [репозиторий задачи с DeepBayes](https://github.com/bayesgroup/deepbayes-2018/tree/master/day1_em) с пустым ноутбуком, формулами, условием.  
* Конечно, это нельзя назвать полноценным проектом, но для меня это было интересным опытом имплементации алгоритма по нетривиальным мат. формулам. Хочется поделиться!
* Мои комментарии помечены надписью **Примечание при выполнении**. Также в ячейке с М-шагом разграничил подсчет параметров.
