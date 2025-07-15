# DS-lab q1
#include <iostream>
#include <vector>
using  namespace std;


bool f_imp(bool p, bool q, bool r) {
    bool left = (p && !q) || r;
    bool right = (!p) || r;
    return (!left) || right; 
}

bool f_bi(bool p, bool q, bool r) {
    bool left = (p && !q) || r;
    bool right = (!p) || r;
    return left == right; 
}

int main() {
    cout << "p q r | (p^¬qvr)->(¬pvr) | (p^¬qvr)<->(¬pvr) \n";
    cout << "-------------------------------------------\n";
    for (int pi = 0; pi < 2; ++pi)
    for (int qi = 0; qi < 2; ++qi)
    for (int ri = 0; ri < 2; ++ri) {
        bool p = pi, q = qi, r = ri;
        bool imp = f_imp(p, q, r);
        bool bi  = f_bi(p, q, r);
        std::cout
            << (p?'T':'F') << " "
            << (q?'T':'F') << " "
            << (r?'T':'F') << " |      "
            << (imp?'T':'F') << "           |      "
            << (bi  ?'T':'F') << "\n";
    }
    return 0;
}
