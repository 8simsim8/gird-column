﻿1.Диапазоны задания и регулировки блоков:

			767px и мешьше		- extra small		    - xs
			768px - 991px		- small					- sm
			992px - 1199px		- medium				- md
			1200 и больше		- large					- lg

2.При ширине экрана меньше 330px - все видимые блоки становятся шириною 100% от ширины экрана и становятся один под одним (установлено разрешение переноса "row-wrap").

3.По умолчанию у колонок внутренний padding слева и справа равен 10px, что дает в сумме 20px межколоночного отступа:
	задается в начале файла:

				@media (min-width: 767px)
					{
					.row
						{
						flex-direction: row;
						}

					.row .col
						{
						margin-bottom: inherit;
						padding: 0 10px;
						}
					}

4.Блок в строке row без padding "no-padding":

		<div class="container">
			<div class="row no-padding">
				<div class="col .../* нужное правило для блока*/"></div>
				.....
				<div class="col .../* нужное правило для блока*/"></div>
			</div>
		</div>

5.Порядок создания блока (12 колонок в сумме):

	- оборачивающий блок "container"
	- блок, создающий строку "row"
	- блок, создающий колонку "col"
	- блокам "col" добавляются все основные правила для элементов

		<div class="container">
			<div class="row">
				<div class="col .../* нужное правило для блока*/"></div>
				.....
				<div class="col .../* нужное правило для блока*/"></div>
			</div>
		</div>

6.Добавить блок нужного количества колонок, в зависимости от ширины окна, добавить к элементу с классом "col":
	где N - количество колонок

			xs-N 								767px и мешьше
			sm-N 								768px - 991px
			md-N 								992px - 1199px
			lg-N 								1200 и больше

7.Отступ нужного количества колонок, добавить к элементу с классом "col":
	где N - количество столбцов

	!!! ВАЖНО - отступ отображается начиная с ключевой точки и больше:

			xs-offset-N 				767px и мешьше
			sm-offset-N 				768px - 991px
			md-offset-N 				992px - 1199px
			lg-offset-N 				1200 и больше

8.Скрыть блок в зависимости от ширины окна, добавить к элементу с классом "col":

	!!! ВАЖНО - элемент будет скрыт в промежутке:

			xs-hidden 					< 767px
			sm-hidden 					768px < 991px
			md-hidden 					992px < 1199px
			lg-hidden 					> 1200px

9.Показать блок в зависимости от ширины окна, добавить к элементу с классом "col":

	!!! ВАЖНО - элемент будет показан в промежутке:

			xs-visible 					< 767px
			sm-visible 					768px < 991px
			md-visible 					992px < 1199px
			lg-visible 					> 1200px

10.По умолчанию, блоки в обертке row размещаются в одну строку ("обертка "container" имеет свойство overflow-x: hidden),
если количество внесенных колонок, больше 12шт, излишки будут скрываться за пределами страницы:

		разрешить перенос блоков на следующюю строчку, можно добавлением к "row" класса:

			row-wrap

11.Выравнивание элементов по вертикали в строке "row":

		 присваивается класс к элементу с классом "row":

			row-top				блоки прижаты к верху строчки
			row-bottom			блоки прижаты к низу строчки
			row-center			блоки по центру строки
			row-stretch			блоки занимают всю доступную высоту строки (по умолчанию)
			row-baseline			блоки выравниваются по базовой линии

12.Выравнивание одного элемента в строке "row":

		 присваивается класс к элементу с классом "col":

			col-top				элемент прижат к верхнему краю строки
			col-bottom			элемент прижат к нижнему краю строки
			col-center			элемент находится по центру строки


13.Изменение размещения блоков в строке "row".
    Исходя из того, в каком дипазоне, необходимо перемещеть блоки, где N-порядковый номер блока в строке:

    !!! ВАЖНО - необходимо пронумеровать все элементы в заданном диапазоне:

            - order-xs-N;
            - order-sm-N;
            - order-md-N;
            - order-lg-N

