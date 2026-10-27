Type of Triangle

Problem: Type of Triangle

Intuition

A valid triangle must satisfy the triangle inequality: the sum of any two sides must be greater than the third side. If any pair of sides adds up to less than or equal to the remaining side, the values do not form a triangle.

A CASE expression checks the conditions in order. First, it identifies invalid triangles. Next, it checks whether all three sides are equal (Equilateral), then whether any two sides are equal (Isosceles). If none of these conditions is true, the triangle is Scalene.

Solution
sql
SELECT
    CASE
        WHEN A + B <= C OR A + C <= B OR B + C <= A
            THEN 'Not A Triangle'
        WHEN A = B AND B = C
            THEN 'Equilateral'
        WHEN A = B OR A = C OR B = C
            THEN 'Isosceles'
        ELSE 'Scalene'
    END
FROM TRIANGLES;
