# project3-pi-estimation
import random

def estimate_pi(total_points):
    points_inside_circle = 0
    
    for _ in range(total_points):
        # Generate random x and y coordinates between 0 and 1
        x = random.random()
        y = random.random()
        
        # Calculate the squared distance from the origin (x^2 + y^2)
        squared_distance = x**2 + y**2
        
        # If the distance is less than or equal to 1, the point is inside the circle
        if squared_distance <= 1:
            points_inside_circle += 1
            
    # Monte Carlo formula to estimate Pi
    pi_estimate = 4 * (points_inside_circle / total_points)
    return pi_estimate

# --- Execution ---
# You can change the number of points to see how the accuracy changes
num_points = 100000
result = estimate_pi(num_points)

print(f"Total points generated: {num_points}")
print(f"Estimated Pi value: {result}")
