/*
Name: Khaled Ahmed
Date: 11/11/2020
Project name: Project 4 vectors
Description: This program uses vectors to access student ids, and test scores from an input file and calculates it all to find the lowest score, highest score, and the average score and sends it to an output file to show the results.
 */

#include <iostream>
#include <iomanip>
#include <fstream>
#include <vector>

using namespace std;

// defining the vectors
typedef vector <int> ivec;
typedef vector <float> fvec;

// prototypes for all of the functions
void setData (ivec&,ivec&,ivec&,ivec&,ifstream&);
void findStAvg(ivec,ivec,ivec,fvec&);
void getInfo(ivec,ivec,ivec,ivec,fvec,ofstream&);
void getHeadings(ofstream&);
void Report(ivec,ivec,ivec,ivec,fvec,ofstream&);
void getHigh(ivec,ofstream&);
void getLow(ivec,ofstream&);
void getAvg(ivec,ofstream&);

int main()
{
    // creating input and output files
    ifstream fileIn;
    ofstream fileOut;
        
    // variables made to have access from vectors
    ivec student_id,quiz1,quiz2,quiz3;
    fvec stud_average;
        
    // function calls
    setData(student_id,quiz1,quiz2,quiz3,fileIn);
    findStAvg(quiz1,quiz2,quiz3,stud_average);
    getInfo(student_id,quiz1,quiz2,quiz3,stud_average,fileOut);

    return 0;
}


void setData(ivec& student_id,ivec& quiz1,ivec& quiz2,ivec& quiz3, ifstream& fileIn)
{
    fileIn.open("pr4data.txt");  //opening the input file to get data
    
    int a,b,c,d;

    if (!fileIn)
    {
        cout << "Could not open the data file";
    }

    else
    {
        while(!fileIn.eof())   // loop to get all of the data until the last line
        {
            fileIn >> a;
            fileIn >> b;
            fileIn >> c;
            fileIn >> d;
            student_id.push_back(a);
            quiz1.push_back(b);
            quiz2.push_back(c);
            quiz3.push_back(d);
            
            fileIn.ignore();
        }
    }

    fileIn.close();
}


void findStAvg(ivec quiz1,ivec quiz2,ivec quiz3,fvec& stud_average)
{
    // finds the average amount of students from the given data
    float average;

    for (int i = 0; i < quiz1.size(); i++)
    {
        stud_average.push_back(average);
        stud_average[i] = (quiz1[i] + quiz2[i] + quiz3[i]) / 3.00;
    }
}


void getInfo(ivec student_id,ivec quiz1,ivec quiz2,ivec quiz3,fvec stud_average,ofstream& fileOut)
{
    fileOut.open("pr4output.txt"); // opens the output file to send info to
        
    fileOut << fixed << setprecision(2) << endl; // sets the decimal points to 2.
        
    getHeadings(fileOut);
    Report(student_id,quiz1,quiz2,quiz3,stud_average,fileOut);
        
    // prints the highest grades for all of the quizzes
    fileOut << "\nHigh score\t";
    getHigh(quiz1,fileOut);
    fileOut << "\t";
    getHigh(quiz2,fileOut);
    fileOut << "\t";
    getHigh(quiz3,fileOut);
        
    // prints the lowest grades for all of the quizzes
    fileOut << "\n\nLow score\t";
    getLow(quiz1,fileOut);
    fileOut << "\t";
    getLow(quiz2,fileOut);
    fileOut << "\t";
    getLow(quiz3,fileOut);
        
    // prints the average grades for all of the quizzes
    fileOut << "\n\nQuiz Average\t";
    getAvg(quiz1,fileOut);
    fileOut << "\t";
    getAvg(quiz2,fileOut);
    fileOut << "\t";
    getAvg(quiz3,fileOut);
        
        
    fileOut.close();
}


void getHeadings(ofstream& fileOut)
{
    // prints the heading titles
    fileOut << "\t" << "CIS Department - Fall 2020" << endl;
    fileOut << "\t" << "CIS 161 Class Statistics" << "\n" << endl;
}


void Report(ivec student_id,ivec quiz1,ivec quiz2,ivec quiz3,fvec stud_average,ofstream& fileOut)
{
    // prints all of the results accumulated from the data
    fileOut << "Student\t\t";
    fileOut << "Quiz 1\t";
    fileOut << "Quiz 2\t";
    fileOut << "Quiz 3\t";
    fileOut << "Average" << endl;
    
    // for loop to print all of the students data
    for (int i = 0; i < student_id.size(); i++)
    {
        fileOut << student_id[i];
        fileOut << "\t\t";
        fileOut << quiz1[i];
        fileOut << "\t";
        fileOut << quiz2[i];
        fileOut << "\t";
        fileOut << quiz3[i];
        fileOut << "\t";
        fileOut << stud_average[i] << endl;
    }
}


void getHigh(ivec test,ofstream& fileOut)
{
    // finds the highest score out of all of the quizzes
    
    int highScore = 00;

    for (int i = 0; i < test.size(); i++)
    {
        if (highScore < test[i])
        {
            highScore = test[i];
        }
    }
    fileOut << highScore; // prints the highest score and gives it to the output file
}


void getLow(ivec test,ofstream& fileOut)
{
    // finds the highest score out of all of the quizzes
    int lowScore = 0;

    for(int i = 0; i < test.size(); i++)
    {
        if (lowScore > test[i])
        {
                lowScore = test[i];
        }
    }
    fileOut << lowScore; // prints the lowest score and gives it to the output file
}

//adds all the grades from a quiz and divides it by the amount of grades, returning the quiz's average
void getAvg(ivec test,ofstream& fileOut)
{
    // adds all of the scores from a quiz and finds the quiz's average
    float averageScore;
    float sum = 0;

    for(int i = 0; i < test.size(); i++)
    {
        sum += test[i];//adds every grade from that quiz
    }
    averageScore = sum / test.size();//divides the total with the number of quiz scores
    fileOut << averageScore;// prints the average score
}

