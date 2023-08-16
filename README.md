class TrafficSensor:
    def __init__(self, location):
        self.location = location
        self.vehicle_count = 0
        self.speed = 0

    def update_data(self, vehicle_count, speed):
        self.vehicle_count = vehicle_count
        self.speed = speed


class TrafficManagementSystem:
    def __init__(self):
        self.sensors = {}

    def add_sensor(self, sensor):
        self.sensors[sensor.location] = sensor

    def predict_congestion(self, location):
        sensor = self.sensors.get(location)
        if sensor:
            if sensor.vehicle_count > threshold or sensor.speed < threshold_speed:
                return "Congested"
            else:
                return "Clear"
        else:
            return "No Data"


# Usage
sensor1 = TrafficSensor("Intersection A")
sensor2 = TrafficSensor("Intersection B")

traffic_system = TrafficManagementSystem()
traffic_system.add_sensor(sensor1)
traffic_system.add_sensor(sensor2)

print(traffic_system.predict_congestion("Intersection A"))
