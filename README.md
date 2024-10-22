#include <iostream>
#include <cmath>

class Cylinder {
private:
    double radius;
    double height;

public:
    Cylinder(double r, double h) : radius(r), height(h) {}

    double volume() {
        return M_PI * pow(radius, 2) * height;
    }

    double surfaceArea() {
        return 2 * M_PI * pow(radius, 2) + 2 * M_PI * radius * height;
    }
};

class Addition {
private:
    int a, b, c;

public:
    Addition() : a(22), b(30), c(50) {}

    int product() {
        return a * b * c;
    }
};

int main() {
    Cylinder cylinder(5.0, 10.0);
    std::cout << "Volume of Cylinder: " << cylinder.volume() << std::endl;
    std::cout << "Surface Area of Cylinder: " << cylinder.surfaceArea() << std::endl;

    Addition addition;
    std::cout << "Product of Integers: " << addition.product() << std::endl;

    return 0;
}

