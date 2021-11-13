/**********************************  water bucket ********************/

#include<stdio.h>
#include<stdlib.h>
#include<stdio_ext.h>

typedef struct{
	int temp;
	int current;
}heater;
int main()
{
	int n;
	printf("1.dial=i-1 for Mannually\n2.dial=i-2 for Automatically\n3.Mobile\n");
	printf("choose mannually or automatically : ");
	scanf("%d",&n);



	if(n==1)                               // mannual mode
	{
	
		char ch;
		int water;                // set initial value of water in bucket
		heater h1;                  // declare heater variable


		puts("current range 0-100");
		__fpurge(stdin);
		printf("set current will passing through heater:");
	       	scanf("%d",&(h1.current));

		for(h1.temp=0; h1.temp<h1.current; h1.temp)
		{

			__fpurge(stdin);
			printf("you want to add water (y/n) : ");
			scanf("%c",&ch);
			if(ch=='y')
			{
			        __fpurge(stdin);
				printf("Add water :");
				scanf("%d",&water);
				h1.temp=h1.temp+h1.current;       //temp=temp+current value
			                                	// if water added than temperature increase according to current
	                               			// otherwise it will increase 1 degree untill reach 100 degree
			        printf("temperature increasing with current\n");
				break;
			}
			
			else
			{
				for(h1.temp=0;h1.temp<=100;h1.temp++);
				printf("temperature incresing\n");
			}


		}
	}


	else if(n==2)                                // AUTOMATIC MODE
	{
		char c;
		heater h;
		int button;
		unsigned char i;
		for(i=0;i<=100;i++)                // for heatup water
		{
			++h.temp;
		}


		__fpurge(stdin);
		printf("Press button:");           // button press means button =true
		scanf("%d",&button);             // give any input

		puts("You are in AUTO-HEATING-ON mode");
		for(h.current=0;h.current<=100;++h.current)
		{
			h.temp=50;
			printf("temperature will remain 50 only \n");
		}
		__fpurge(stdin);
		printf("You want to dial i-1 (y/n):");
		scanf("%c",&c);

		if(c=='y')
		{
		       int t;
		       
	
			__fpurge(stdin);
			printf("Dial:");
			scanf("%d",&n);
		      __fpurge(stdin);
		      scanf("%d",&t);
		      
	             	      
							//clockwise t increase
			                                   // anticlockwise t will decrease
			if((n==1)&&(t++))
			{

				for(i=0;i<=100;i++)        // temperature increase
					++h.temp;
			}
			else if((n==1)&&(t--))             //temperature decrease
			{
				for(i=100;i>=0;i--)
					--h.temp;
			}

			else if(n==2)
			{
				puts("EXIT FROM AUTO HEATING MODE");
				exit(1);
			}
		}
	}

	else if(n==3)
		{
			 char m;

			heater h2;
			__fpurge(stdin);
			printf(" You want to set temperature(y/n):");
			scanf("%c",&m);
			if(m=='y')
			{
				__fpurge(stdin);
				printf("set temp in degree :"); 
			        scanf("%d",&(h2.temp));
			}
			else
				return 0;
		}
	else;
}

		
