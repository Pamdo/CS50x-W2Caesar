# CS50x-CaesarTrain0
# Basic Text Encryption on C
# Get a massage and determine a key.
# No solver yet.



#include <stdio.h>
#include <cs50.h>
#include <string.h>

int main(int argc, string argv[])
{
    //GET SECRET MASSAGE
    string massage = get_string("WRITE THE SECRET MASSAGE\n");
    //GET SOLVER KOD
    const int KEY = get_int("ENTER THE KEY NUMBER\n");
    //MASSAGE'S LENGTH
    int mas_num = strlen(massage);
    //ENCRYPTED MASSAGE ARRAY
    int mod_massage[mas_num];
    for (int i=0 ; i<mas_num ; i++)
    {
        if (massage[i]<91&&massage[i]>=64)
        {
            if(massage[i]+KEY%26<91)
            { 
                mod_massage[i] = massage[i]+KEY%26;
            }
            else
            {
                mod_massage[i] = massage[i]+KEY%26-26;
            }
        }       
        else if (massage[i]<123&&massage[i]>96)
            {
                if(massage[i]+KEY%26<123)
                { 
                    mod_massage[i] = massage[i]+KEY%26;
                }
                else
                {
                    mod_massage[i] = massage[i]+KEY%26-26;
                }
            }
        else
        {
            mod_massage[i] = massage[i];
        }    
    }
    for (int i=0 ; i<mas_num ; i++)
    {
        printf("%c",mod_massage[i]);
    }
    printf("\n");
}

