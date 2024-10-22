#include <iostream>
#include <stdexcept>
#include <cmath>

const double PI = 3.14159265358979323846;

class Cylinder {
private:
    double radius;
    double height;

public:
    // Constructor to initialize radius and height
    Cylinder(double r, double h) {
        if (r < 0 || h < 0) {
            throw std::invalid_argument("Radius and height must be non-negative.");
        }
        radius = r;
        height = h;
    }

    // Function to calculate the volume of the cylinder
    double volume() const {
        return PI * std::pow(radius, 2) * height;
    }

    // Function to calculate the surface area of the cylinder
    double surfaceArea() const {
        return 2 * PI * std::pow(radius, 2) + 2 * PI * radius * height;
    }

    // Function to output the volume and surface area
    void display() const {
        std::cout << "Volume of the cylinder: " << volume() << std::endl;
        std::cout << "Surface area of the cylinder: " << surfaceArea() << std::endl;
    }
};

class Addition {
private:
    int a, b, c;

public:
    // Constructor to initialize integers
    Addition() : a(22), b(30), c(50) {}

    // Function to calculate the product of the integers
    int product() const {
        return a * b * c;
    }

    // Function to output the product
    void display() const {
        std::cout << "Product of the integers: " << product() << std::endl;
    }
};

int main() {
    try {
        // Create a Cylinder object
        Cylinder cylinder(5.0, 10.0);
        cylinder.display();

        // Create an Addition object
        Addition addition;
        addition.display();
    } catch (const std::invalid_argument& e) {
        std::cerr << "Error: " << e.what() << std::endl;
    } catch (const std::exception& e) {
        std::cerr << "An unexpected error occurred: " << e.what() << std::endl;
    }

    return 0;
}

