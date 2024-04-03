#include <iostream>
#include <string>
using namespace std;

void total(int* sum, int cash, int d) {
    *sum += cash * d;
}

int main() {

    int a;
    int b;
    char c;
    int d;
    int sum = 0;

    string menu[] = {"일반 라면", "김치 라면", "치즈 라면", "떡 라면", "떡 만두 라면"};
    int prices[] = {3500, 4000, 4200, 4300, 4500};

    do{
    cout << "***** 슈니의 라면가게에 오신 것을 환영합니다 *****" << endl << endl;

    for (a = 0; a < 5; ++a) {
        
        cout << a+1 << ". " << menu[a] << "(" << prices[a] << ")" << endl;
       
        }

        cout << endl;
        cout << "구매하실 라면 변호를 입력해 주세요(종료는 0) : ";
        cin >> b;

        if (b == 0) {
            cout << "총 가격은 " << sum << "원 입니다." << endl;
            break;
        }

        if (b < 1 || b > 5) {
            cout << "제대로 된 숫자를 입력해 주세요." << endl;
            continue;
        }

        cout << menu[b-1] << "을(를) 구매하시겠습니까? (Y/N)";
        cin >> c;
        cout << endl;

        if (c == 'N') {
            continue;
        }
        else if(c == 'Y') {
            cout << "구매하실 라면 개수를 입력해 주세요 : ";
            cin >> d;
            cout << menu[b-1] << d << "개 구매하셨습니다." << endl;
            cout << "가격은 " << prices[b-1] * d << "원 입니다." << endl;
            int cash = prices[b-1];
            total(&sum, cash, d);
        }

        else {
            cout << "잘못된 선택입니다. 다시 입력해주세요." << endl;
        }
   
            }
    while (true);
     
    return 0;
}
