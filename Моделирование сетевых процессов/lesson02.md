### Лекция 2

###Менеджеры компоновки

Классы компоновки виджетов являются одной из сильных сторон библиотеки  qt, так как они представляют собой контейнеры, которые после изменения размеров окна автоматически приводят в соответствующие размеры и координаты виджеты, находящиеся в нем. Они представляют возможности вертикального, горизонтального размещения. Они управляют не только виджетами, но и другими компоновками.

QLayout - наследован от QLayoutItem и QObject. Абстрактный класс, от него наследовать объект не получиться. 

QBoxLayout - выравнивает виджеты горизонтально или вертикально
	LeftToRight
	RightToLeft
	TopToBottom - вертикальное размещение сверху вниз
	BottomToTop - вертикальное размещение снизу вверх

###Пример 1 QBoxLayout

int main(int argc, char** argv)
{
	QApplication.app(argc, argv);
	QWidget wgt;
	QPushButton* pcmdA= new QPushButton("A");
	QPushButton* pcmdB= new QPushButton("B");
	QPushButton* pcmdC= new QPushButton("C");
	QBoxLayout* pbxLayout = new QBoxLayout(QBoxLayout::LeftToRight);
	pbxLayout->addWidget(pcmdA, 1);
	pbxLayout->addWidget(pcmdB, 2);
	pbxLayout->addWidget(pcmdC, 3);
	wgt.setLayout(pbxLayout);
	wgt.resize(450, 40);
	wgt.show();
	return app.exec();
}
QHBoxLayout - горизонтальное размещение слева-направо, не может менять правило размещения
QVBoxLayout - вертикальное размещение сверху-вниз. 

QGridLayout - таблица