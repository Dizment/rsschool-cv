My English is perfect.
I'am study in BSU on RFKIT.

```
int main()
{
	int row; cout << "\n Wwedite stroku: "; cin >> row;
	int column; cout << "\n Wwedite stolbec: "; cin >> column; column++;

	double **A = createMatrix(row, column);
	
	ifstream in("file.txt");
	enterMatrix(A, row, column, in);
	in.close();

	double **B = createMatrix(row, column);
	copyMatrix(A, B, row, column);
	cout << endl << endl;
	viewMatrix(B, row, column);

	double *Answer = new double[row];

	if (Gauss(Answer, B, row, column) == 1)
	{
		cout << endl << " Answer\n\n";
		viewAnswer(Answer, row);

		double *Nev = new double[row];
		VecNev(Nev, Answer, A, row, column);

		delete Nev;
	}
	else cout << "\n Error!\n\n";
	delete Answer;
	deleteMatrix(B, row);
	deleteMatrix(A, row);
}
```
