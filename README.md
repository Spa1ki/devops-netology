Задача 1
Опишите кратко, в чём основное отличие полной (аппаратной) виртуализации, паравиртуализации и виртуализации на основе ОС.
Ответ
Виртуальные машины используют собственные виртуальные устройства и ядра, а также позволяют работать с различными ОС. Контейнеры монтируют устройства и используют одно ядро, работают как процесс текущей системы. Работа с контейнерами занимает меньше времени.

Задача 2
Выберите один из вариантов использования организации физических серверов в зависимости от условий использования.
Организация серверов:
физические сервера,
паравиртуализация,
виртуализация уровня ОС.
Условия использования:
высоконагруженная база данных, чувствительная к отказу;
различные web-приложения;
Windows-системы для использования бухгалтерским отделом;
системы, выполняющие высокопроизводительные расчеты на GPU.
Опишите, почему вы выбрали к каждому целевому использованию такую организацию.
Ответ
Физические сервера 
a. Системы, выполняющие высокопроизводительные расчеты на GPU ( в связи с необходимостью выделения больших мощностей лучше выделить отдельный физический сервер под целевые нужды. Не ограничивая потребление ресурсов.)
b. Высоконагруженная база данных, чувствительная к отказу (В случае роста нагрузки будут использованы все имеющиеся ресурсы, а не только выделенные. Меньше вероятность отказа.) 
Паравиртуализация
a.Windows-системы для использования бухгалтерским отделом (Собственная ВМ на отдельном ядре ОС не влияющая на работу других ВМ. Позволяет легко обновляться)  
Виртуализация уровня ОС
a. Различные web-приложения (быстрое развертывание позволяет тратить меньше времени при обновлениях. Можно отдельно ограничить потребление ресурсов, для отдельных сервисов приложения. Не требовательно к ОС) 

Задача 3
Выберите подходящую систему управления виртуализацией для предложенного сценария. Детально опишите ваш выбор.
Сценарии:
100 виртуальных машин на базе Linux и Windows, общие задачи, нет особых требований. Преимущественно Windows based-инфраструктура, требуется реализация программных балансировщиков нагрузки, репликации данных и автоматизированного механизма создания резервных копий.
Требуется наиболее производительное бесплатное open source-решение для виртуализации небольшой (20-30 серверов) инфраструктуры на базе Linux и Windows виртуальных машин.
Необходимо бесплатное, максимально совместимое и производительное решение для виртуализации Windows-инфраструктуры.
Необходимо рабочее окружение для тестирования программного продукта на нескольких дистрибутивах Linux.

Ответ
VMWare
Не имеет ограничений по ОС. Имеют общие драйвера устройств.  Поддерживает все необходимые требования. Возможность распределения ресурсов исходя из нужд каждой ВМ.  Гибкая настройка Бэкапов для каждой ВМ
Xen PV
Предоставляет высокую производительность и быструю развертку. Имеет возможность развертывания по шаблонам. Позволяет работать с разными ОС.
Xen PV или VMware ESXi
Показывают наиболее высокую производительность, а также совместимы с ОС Windows.
KVM или XEN HVM
Лучшее решение для работы с Linux дистрибутивами.  Высокая производительность.

Задача 4
Опишите возможные проблемы и недостатки гетерогенной среды виртуализации (использования нескольких систем управления виртуализацией одновременно) и что необходимо сделать для минимизации этих рисков и проблем. Если бы у вас был выбор, создавали бы вы гетерогенную среду или нет? Мотивируйте ваш ответ примерами.

Ответ
Для использования подобной среды необходимо разворачивать разные системы управления ВМ на отдельных серверах. Для разных ОС приоритетно использование разных систем управления ВМ. Объединение их в одну оснастку для управления не всегда возможно. Управление подобного рода средой довольно сложный процесс и неудобный. Но есть и свои плюсы в более качественной работе с разными ОС. Некоторые программы ставятся поверх ОС.

При выборе все зависело бы от того какие ОС мне нужны и в каком количестве. Если трудозатраты будут того стоить я бы конечно воспользовался. Если к примеру мне потребуется иметь пару сотен ВМ на ОС Linux  и так же на Windows. И мне потребуется ВМ с эмуляцией железа или без. 

