# Train-case1
import java.io.*;
import java.util.*;
class test1
{
public static void main(String args[])
{
int l_pop1,l_pop2,l_pop3,m_pop1,m_pop2,m_pop3;
int flag1=0,flag2=0,flag3=0,ch;
int pn_m[]={22,119,64,177,21};
int pn_t[]={22,111,87,193,22};
		int pn_w[]={11,107,93,162,42};
		double dt[]={6.04,9.04,12.04,15.04,19.04};
		Scanner sc=new Scanner(System.in);
		do
		{
		System.out.println("Enter your choice of operation:1.Displaying train details\n2.Finding popular train\n3.Finding least popular train\n4.Finding 6.04 is popular than 9.04 or not\n5.If 6.04 on monday is popular than 6.04 on tuesday");
		System.out.println("6.Finding popular train by your choice\n7.Display passenger no below 50\n8.Average no of passengers on 12.04 train\n9.Average no of passengers on train of your choice\n10.Quit");
		ch=sc.nextInt();
		switch(ch)
		{
		//Question a
		case 1:System.out.println("day \t\t dep time \t\t no of pass\t\t");
		for(int i=0;i<=4;i++)
		{
			System.out.println("monday\t\t"+dt[i]+"\t\t\t"+pn_m[i]);
		}
		for(int i=0;i<=4;i++)
		{
			System.out.println("tuesday\t\t"+dt[i]+"\t\t\t"+pn_t[i]);
		}
		for(int i=0;i<=4;i++)
		{
			System.out.println("wednesday\t\t"+dt[i]+"\t\t\t"+pn_w[i]);
		}break;
		//Question b
		case 2:m_pop1=pn_m[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_m[i]>m_pop1)
			{m_pop1=pn_m[i];
			flag1=i;}
		}
		m_pop2=pn_t[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_t[i]>m_pop2)
			{m_pop2=pn_t[i];
			flag2=i;}
		}
		m_pop3=pn_w[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_w[i]>m_pop3)
			{m_pop3=pn_w[i];
			flag3=i;}
		}
		if(m_pop1>m_pop2 && m_pop1>m_pop3)
		{
		System.out.println("the popular train is on monday and the time is "+dt[flag1]);
		}
		if(m_pop1<m_pop2 && m_pop2>m_pop3)
		{
		System.out.println("the popular train is on tuesday and the time is "+dt[flag2]);
		}
		if(m_pop3>m_pop2 && m_pop1<m_pop3)
		{
		System.out.println("the popular train is on wednesday and the time is "+dt[flag3]);
		}break;
		//Question c
		case 3:l_pop1=pn_m[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_m[i]<l_pop1)
			{l_pop1=pn_m[i];
			flag1=i;}
		}
		l_pop2=pn_t[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_t[i]<l_pop2)
			{l_pop2=pn_t[i];
			flag2=i;}
		}
		l_pop3=pn_w[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_w[i]<l_pop3)
			{l_pop3=pn_w[i];
			flag3=i;}
			else
			flag3=0;
		}
		if(l_pop1<l_pop2 && l_pop1<l_pop3)
		{
		System.out.println("the least popular train is on monday and the time is "+dt[flag1]);
		}
		if(l_pop1>l_pop2 && l_pop2<l_pop3)
		{
		System.out.println("the least popular train is on tuesday and the time is "+dt[flag2]);
		}
		if(l_pop3<l_pop2 && l_pop1>l_pop3)
		{
		System.out.println("the least popular train is on wednesday and the time is "+dt[flag3]);
		}break;
		//Question d
		case 4:if((pn_m[0]<pn_m[1] && pn_t[0]<pn_t[1]) || (pn_m[0]<pn_m[1] && pn_w[0]<pn_w[1]) || (pn_t[0]<pn_t[1] && pn_w[0]<pn_w[1]))
		{
		System.out.println("the popular train time is 9.04");
		}
		else
		{System.out.println("the popular train time is 6.04");}break;
		//Question e
		case 5:for(int i=0;i<5;i++)
		{
			if(pn_m[i]<pn_t[i])
			{
			flag1++;
			}
		}
		if(flag1>3)
		{System.out.println("the popular train is tuesday");}
		else
		{System.out.println("the popular train is monday");}break;
		//Question f
		case 6:System.out.println("Enter train day and time");
		double d1,d2;int x=0,y=0;
		String a,b;
		d1=sc.nextDouble();
		d2=sc.nextDouble();
		a=sc.next();
		b=sc.next();
		if(a.equals("monday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d1)
		{x=pn_m[i];}
		}}		
		if(a.equals("tuesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d1)
		{x=pn_t[i];}
		}}		
		if(a.equals("wednesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d1)
		{x=pn_w[i];}
		}}
		if(b.equals("monday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d2)
		{y=pn_m[i];}
		}}		
		if(b.equals("tuesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d2)
		{y=pn_t[i];}
		}}		
		if(b.equals("wednesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d2)
		{y=pn_w[i];}
		}}
		if(x>y)
		{System.out.println("first train is popular");}
		else
		{System.out.println("second train is popular");}		
		break;
		//Question f1
		case 7:for(int i=0;i<5;i++)
		{
			if(pn_m[i]<50)
			{
			System.out.println("the train with passengers less than 50 on monday timing is"+dt[i]);
			}
			if(pn_t[i]<50)
			{
			System.out.println("the train with passengers less than 50 on tuesday timing is"+dt[i]);
			}
			if(pn_w[i]<50)
			{
			System.out.println("the train with passengers less than 50 on wednesday timing is"+dt[i]);
			}
		}break;
		//Question g
		case 8:int avg;
		avg=(pn_m[2]+pn_t[2]+pn_w[2])/3;
		System.out.println("average no of passengers travelling on 12.04 train is "+avg);
		break;
		case 9:String day;
		int s=0;
		System.out.println("Enter day for average no of passengers travelling on the train");
		day=sc.next();
		if(day.equals("monday"))
		{
		for(int i=0;i<5;i++)
		{s=s+pn_m[i];}
		System.out.println("Average no of passengers travelling on monday is "+s/5);
		}
		else if(day.equals("tuesday"))
		{
		for(int i=0;i<5;i++)
		{s=s+pn_t[i];}
		System.out.println("Average no of passengers travelling on tuesday is "+s/5);
		}
		else if(day.equals("wednesday"))
		{		
		for(int i=0;i<5;i++)
		{s=s+pn_w[i];}
		System.out.println("Average no of passengers travelling on wednesday is "+s/5);
		}
		break;
		case 10:System.out.println("exit");
		break;
		}
		}while(ch!=10);
		
	}
	
}


		int pn_w[]={11,107,93,162,42};
		double dt[]={6.04,9.04,12.04,15.04,19.04};
		Scanner sc=new Scanner(System.in);
		do
		{
		System.out.println("Enter your choice of operation:1.Displaying train details\n2.Finding popular train\n3.Finding least popular train\n4.Finding 6.04 is popular than 9.04 or not\n5.If 6.04 on monday is popular than 6.04 on tuesday");
		System.out.println("6.Finding popular train by your choice\n7.Display passenger no below 50\n8.Average no of passengers on 12.04 train\n9.Average no of passengers on train of your choice\n10.Quit");
		ch=sc.nextInt();
		switch(ch)
		{
		//Question a
		case 1:System.out.println("day \t\t dep time \t\t no of pass\t\t");
		for(int i=0;i<=4;i++)
		{
			System.out.println("monday\t\t"+dt[i]+"\t\t\t"+pn_m[i]);
		}
		for(int i=0;i<=4;i++)
		{
			System.out.println("tuesday\t\t"+dt[i]+"\t\t\t"+pn_t[i]);
		}
		for(int i=0;i<=4;i++)
		{
			System.out.println("wednesday\t\t"+dt[i]+"\t\t\t"+pn_w[i]);
		}break;
		//Question b
		case 2:m_pop1=pn_m[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_m[i]>m_pop1)
			{m_pop1=pn_m[i];
			flag1=i;}
		}
		m_pop2=pn_t[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_t[i]>m_pop2)
			{m_pop2=pn_t[i];
			flag2=i;}
		}
		m_pop3=pn_w[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_w[i]>m_pop3)
			{m_pop3=pn_w[i];
			flag3=i;}
		}
		if(m_pop1>m_pop2 && m_pop1>m_pop3)
		{
		System.out.println("the popular train is on monday and the time is "+dt[flag1]);
		}
		if(m_pop1<m_pop2 && m_pop2>m_pop3)
		{
		System.out.println("the popular train is on tuesday and the time is "+dt[flag2]);
		}
		if(m_pop3>m_pop2 && m_pop1<m_pop3)
		{
		System.out.println("the popular train is on wednesday and the time is "+dt[flag3]);
		}break;
		//Question c
		case 3:l_pop1=pn_m[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_m[i]<l_pop1)
			{l_pop1=pn_m[i];
			flag1=i;}
		}
		l_pop2=pn_t[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_t[i]<l_pop2)
			{l_pop2=pn_t[i];
			flag2=i;}
		}
		l_pop3=pn_w[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_w[i]<l_pop3)
			{l_pop3=pn_w[i];
			flag3=i;}
			else
			flag3=0;
		}
		if(l_pop1<l_pop2 && l_pop1<l_pop3)
		{
		System.out.println("the least popular train is on monday and the time is "+dt[flag1]);
		}
		if(l_pop1>l_pop2 && l_pop2<l_pop3)
		{
		System.out.println("the least popular train is on tuesday and the time is "+dt[flag2]);
		}
		if(l_pop3<l_pop2 && l_pop1>l_pop3)
		{
		System.out.println("the least popular train is on wednesday and the time is "+dt[flag3]);
		}break;
		//Question d
		case 4:if((pn_m[0]<pn_m[1] && pn_t[0]<pn_t[1]) || (pn_m[0]<pn_m[1] && pn_w[0]<pn_w[1]) || (pn_t[0]<pn_t[1] && pn_w[0]<pn_w[1]))
		{
		System.out.println("the popular train time is 9.04");
		}
		else
		{System.out.println("the popular train time is 6.04");}break;
		//Question e
		case 5:for(int i=0;i<5;i++)
		{
			if(pn_m[i]<pn_t[i])
			{
			flag1++;
			}
		}
		if(flag1>3)
		{System.out.println("the popular train is tuesday");}
		else
		{System.out.println("the popular train is monday");}break;
		//Question f
		case 6:System.out.println("Enter train day and time");
		double d1,d2;int x=0,y=0;
		String a,b;
		d1=sc.nextDouble();
		d2=sc.nextDouble();
		a=sc.next();
		b=sc.next();
		if(a.equals("monday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d1)
		{x=pn_m[i];}
		}}		
		if(a.equals("tuesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d1)
		{x=pn_t[i];}
		}}		
		if(a.equals("wednesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d1)
		{x=pn_w[i];}
		}}
		if(b.equals("monday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d2)
		{y=pn_m[i];}
		}}		
		if(b.equals("tuesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d2)
		{y=pn_t[i];}
		}}		
		if(b.equals("wednesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d2)
		{y=pn_w[i];}
		}}
		if(x>y)
		{System.out.println("first train is popular");}
		else
		{System.out.println("second train is popular");}		
		break;
		//Question f1
		case 7:for(int i=0;i<5;i++)
		{
			if(pn_m[i]<50)
			{
			System.out.println("the train with passengers less than 50 on monday timing is"+dt[i]);
			}
			if(pn_t[i]<50)
			{
			System.out.println("the train with passengers less than 50 on tuesday timing is"+dt[i]);
			}
			if(pn_w[i]<50)
			{
			System.out.println("the train with passengers less than 50 on wednesday timing is"+dt[i]);
			}
		}break;
		//Question g
		case 8:int avg;
		avg=(pn_m[2]+pn_t[2]+pn_w[2])/3;
		System.out.println("average no of passengers travelling on 12.04 train is "+avg);
		break;
		case 9:String day;
		int s=0;
		System.out.println("Enter day for average no of passengers travelling on the train");
		day=sc.next();
		if(day.equals("monday"))
		{
		for(int i=0;i<5;i++)
		{s=s+pn_m[i];}
		System.out.println("Average no of passengers travelling on monday is "+s/5);
		}
		else if(day.equals("tuesday"))
		{
		for(int i=0;i<5;i++)
		{s=s+pn_t[i];}
		System.out.println("Average no of passengers travelling on tuesday is "+s/5);
		}
		else if(day.equals("wednesday"))
		{		
		for(int i=0;i<5;i++)
		{s=s+pn_w[i];}
		System.out.println("Average no of passengers travelling on wednesday is "+s/5);
		}
		break;
		case 10:System.out.println("exit");
		break;
		}
		}while(ch!=10);
		
	}
	
}


		int pn_w[]={11,107,93,162,42};
		double dt[]={6.04,9.04,12.04,15.04,19.04};
		Scanner sc=new Scanner(System.in);
		do
		{
		System.out.println("Enter your choice of operation:1.Displaying train details\n2.Finding popular train\n3.Finding least popular train\n4.Finding 6.04 is popular than 9.04 or not\n5.If 6.04 on monday is popular than 6.04 on tuesday");
		System.out.println("6.Finding popular train by your choice\n7.Display passenger no below 50\n8.Average no of passengers on 12.04 train\n9.Average no of passengers on train of your choice\n10.Quit");
		ch=sc.nextInt();
		switch(ch)
		{
		//Question a
		case 1:System.out.println("day \t\t dep time \t\t no of pass\t\t");
		for(int i=0;i<=4;i++)
		{
			System.out.println("monday\t\t"+dt[i]+"\t\t\t"+pn_m[i]);
		}
		for(int i=0;i<=4;i++)
		{
			System.out.println("tuesday\t\t"+dt[i]+"\t\t\t"+pn_t[i]);
		}
		for(int i=0;i<=4;i++)
		{
			System.out.println("wednesday\t\t"+dt[i]+"\t\t\t"+pn_w[i]);
		}break;
		//Question b
		case 2:m_pop1=pn_m[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_m[i]>m_pop1)
			{m_pop1=pn_m[i];
			flag1=i;}
		}
		m_pop2=pn_t[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_t[i]>m_pop2)
			{m_pop2=pn_t[i];
			flag2=i;}
		}
		m_pop3=pn_w[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_w[i]>m_pop3)
			{m_pop3=pn_w[i];
			flag3=i;}
		}
		if(m_pop1>m_pop2 && m_pop1>m_pop3)
		{
		System.out.println("the popular train is on monday and the time is "+dt[flag1]);
		}
		if(m_pop1<m_pop2 && m_pop2>m_pop3)
		{
		System.out.println("the popular train is on tuesday and the time is "+dt[flag2]);
		}
		if(m_pop3>m_pop2 && m_pop1<m_pop3)
		{
		System.out.println("the popular train is on wednesday and the time is "+dt[flag3]);
		}break;
		//Question c
		case 3:l_pop1=pn_m[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_m[i]<l_pop1)
			{l_pop1=pn_m[i];
			flag1=i;}
		}
		l_pop2=pn_t[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_t[i]<l_pop2)
			{l_pop2=pn_t[i];
			flag2=i;}
		}
		l_pop3=pn_w[0];
		for(int i=1;i<=4;i++)
		{
			if(pn_w[i]<l_pop3)
			{l_pop3=pn_w[i];
			flag3=i;}
			else
			flag3=0;
		}
		if(l_pop1<l_pop2 && l_pop1<l_pop3)
		{
		System.out.println("the least popular train is on monday and the time is "+dt[flag1]);
		}
		if(l_pop1>l_pop2 && l_pop2<l_pop3)
		{
		System.out.println("the least popular train is on tuesday and the time is "+dt[flag2]);
		}
		if(l_pop3<l_pop2 && l_pop1>l_pop3)
		{
		System.out.println("the least popular train is on wednesday and the time is "+dt[flag3]);
		}break;
		//Question d
		case 4:if((pn_m[0]<pn_m[1] && pn_t[0]<pn_t[1]) || (pn_m[0]<pn_m[1] && pn_w[0]<pn_w[1]) || (pn_t[0]<pn_t[1] && pn_w[0]<pn_w[1]))
		{
		System.out.println("the popular train time is 9.04");
		}
		else
		{System.out.println("the popular train time is 6.04");}break;
		//Question e
		case 5:for(int i=0;i<5;i++)
		{
			if(pn_m[i]<pn_t[i])
			{
			flag1++;
			}
		}
		if(flag1>3)
		{System.out.println("the popular train is tuesday");}
		else
		{System.out.println("the popular train is monday");}break;
		//Question f
		case 6:System.out.println("Enter train day and time");
		double d1,d2;int x=0,y=0;
		String a,b;
		d1=sc.nextDouble();
		d2=sc.nextDouble();
		a=sc.next();
		b=sc.next();
		if(a.equals("monday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d1)
		{x=pn_m[i];}
		}}		
		if(a.equals("tuesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d1)
		{x=pn_t[i];}
		}}		
		if(a.equals("wednesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d1)
		{x=pn_w[i];}
		}}
		if(b.equals("monday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d2)
		{y=pn_m[i];}
		}}		
		if(b.equals("tuesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d2)
		{y=pn_t[i];}
		}}		
		if(b.equals("wednesday"))
		{
		for(int i=0;i<5;i++)
		{
		if(dt[i]==d2)
		{y=pn_w[i];}
		}}
		if(x>y)
		{System.out.println("first train is popular");}
		else
		{System.out.println("second train is popular");}		
		break;
		//Question f1
		case 7:for(int i=0;i<5;i++)
		{
			if(pn_m[i]<50)
			{
			System.out.println("the train with passengers less than 50 on monday timing is"+dt[i]);
			}
			if(pn_t[i]<50)
			{
			System.out.println("the train with passengers less than 50 on tuesday timing is"+dt[i]);
			}
			if(pn_w[i]<50)
			{
			System.out.println("the train with passengers less than 50 on wednesday timing is"+dt[i]);
			}
		}break;
		//Question g
		case 8:int avg;
		avg=(pn_m[2]+pn_t[2]+pn_w[2])/3;
		System.out.println("average no of passengers travelling on 12.04 train is "+avg);
		break;
		case 9:String day;
		int s=0;
		System.out.println("Enter day for average no of passengers travelling on the train");
		day=sc.next();
		if(day.equals("monday"))
		{
		for(int i=0;i<5;i++)
		{s=s+pn_m[i];}
		System.out.println("Average no of passengers travelling on monday is "+s/5);
		}
		else if(day.equals("tuesday"))
		{
		for(int i=0;i<5;i++)
		{s=s+pn_t[i];}
		System.out.println("Average no of passengers travelling on tuesday is "+s/5);
		}
		else if(day.equals("wednesday"))
		{		
		for(int i=0;i<5;i++)
		{s=s+pn_w[i];}
		System.out.println("Average no of passengers travelling on wednesday is "+s/5);
		}
		break;
		case 10:System.out.println("exit");
		break;
		}
		}while(ch!=10);
		
	}
	
}

