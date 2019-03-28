# -.-throw-.-121
Генерация исключений. throw . #121
void Foo(int value)
{
	if (value<0)
	{
        throw value;//надо указать что хотим бросить в исключение в catch, например, число, строку или класс :exception 
		//throw "Число меньше 0!!!";//пример передачи в throw строки
		//throw exception("Число меньше нуля");
	}
	
	cout << "Переменная= " << value<<endl;
}
int main()
{
	setlocale(LC_ALL, "ru");
	try
	{
     Foo(55);//если сюда бросили целое число, то и ловить ошибку в catch н.
	 //с целым числом. Сюда м. передать любое число
	 //т е catch (const int ex). Если строку то catch (const char *ex)
	} 
	catch (const int ex)//(const exception &ex)-для классов исключений. это более универсальное решение
	{
		cout << "Мы поймали " << ex<<endl;
		//cout << "Мы поймали " << ex.what() << endl;//для классов исключений.это более универсальное решение
	}
	
	return 0;
}
