# BowlingUpdate.cpp
#include <iostream>
#include <string>

using namespace std;

int main()
{



	const int frame = 10;
	int roll = 0;
	int scores[frame];
	int Total;
	string num;
	num = ('1', '2', '3', '4', '5', '6', '7', '8', '9', '/', 'X');


	cout << "Enter bowling scores for a game: ";
	cin >> scores[frame];

	if (roll == 1)
	{
		if (frame > 10)
		{
			if (scores[frame] == 10)
			{

				cout << "Strike" << endl;


			}
			else if (scores[frame] > 10)
			{

				cout << scores << endl;


			}


			else if (roll == 2)
			{

				if (scores[frame] == 10)
				{

					cout << "Spare" << endl;


				}
				else if (scores[frame] > 10)
				{

					cout << scores << endl;


				}


				else if (roll == 3)
				{
					if (frame == 10)
					{
						if (scores[frame] == 10)
						{

							cout << "Strike" << endl;

						}
						else if (scores[frame] > 10)
						{

							cout << scores << endl;


						}

					}

				}
			}
		}
	}

	cout << "Frames: " << endl;
	cout << '1' << '\t' << '2' << '\t' << '3' << '\t' << '4' << '\t' << '5';
	cout << '\t' << '6' << '\t' << '7' << '\t' << '8' << '\t' << '9' << '\t' << "10" << endl;
	cout << "---------------------------------------------------------------------------" << endl;




	cout << "Total score: " << Total << endl;




	cin.ignore();
	cin.get();
	return 0;

}

// Update to looped Bowling Tournment
int main()
{
	{
		int x[][4], j, i, a[4][];
		for (i = 0; ; i++)                        /*the frist round gets the score*/
		{
			scanf("%d", &x[i][0]);
			if (x[i][0] != 10)
			{
				scanf("%d", &x[i][1]);       /*if the frist round could not get the 10 score, input the second round score*/
			}
			printf("\n");
		}
		for (i = 0; ; i++)
		{                                       /*calculate every frame score exclude the i-1 round frame*/
			if (x[i][0] == 10)
			{
				x[i][1] = 0;
				if (x[i + 1][0] == 10)    x[i][2] = 20 + x[i + 2][0];
				else x[i][2] = 10 + x[i + 1][0] + x[i + 1][1];
			}
			else if (x[i][0] + x[i][1] == 10)
				x[i][2] = 10 + x[i + 1][0];
			else x[i][2] = x[i][0] + x[i][1];
		}
		if (x[i - 1][0] == 10)
		{                                        /*the score get from i frame*/
			if (x[i][0] == 10)    x[i - 1][2] = 20;
			else x[i - 1][2] = 10 + x[i][0] + x[i][1];
		}
		else if (x[i - 1][0] + x[i - 1][1] == 10)   x[i - 1][2] = 10 + x[i][0];
		else x[i - 1][2] = x[i - 1][0] + x[i - 1][1];
		x[0][3] = x[0][2];
		for (i = 1; ; i++)                                   /*calculate the total score*/
			x[i][3] = x[i][2] + x[i - 1][3];
		x[i - 1][3] = x[i - 1][2] + x[i - 2][3];
		for (i = 0; ; i++)
			for (j = 0; j < 4; j++)
				a[j][i] = x[i][j];                               /*exchange the two array*/
		a[0][i] = x[i][0];
		a[1][i] = x[i][1];
		for (j = 0; j < 2; j++)
		{
			for (i = 0; i < 11; i++)                     /*calculate the score in every frame */
				printf("%5d", a[j][i]);
			printf("\n");
		}
		for (j = 2; j < 4; j++)
		{                                         /*calculate every frame score and total score*/
			for (i = 0; i < 10; i++)
				printf("%5d", a[j][i]);
			printf("\n");
		}
	}
	return 0;
}
