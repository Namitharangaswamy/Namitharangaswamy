- 👋 Hi, I’m @Namitharangaswamy
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Namitharangaswamy/Namitharangaswamy is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import time

class TrafficLightControlSystem:
    def __init__(self):
        # Define traffic light states
        self.states = ['Green_NS', 'Yellow_NS', 'Red_NS', 'Green_EW', 'Yellow_EW', 'Red_EW']
        self.current_state = 'Green_NS'
        self.state_timings = {'Green_NS': 10, 'Yellow_NS': 3, 'Red_NS': 10, 'Green_EW': 10, 'Yellow_EW': 3, 'Red_EW': 10}

    def transition_to(self, new_state):
        print(f'Transitioning from {self.current_state} to {new_state}')
        self.current_state = new_state

    def run_traffic_light_system(self):
        try:
            while True:
                self.transition_to('Yellow_NS')  # Transition from Green_NS to Yellow_NS
                time.sleep(self.state_timings['Yellow_NS'])

                self.transition_to('Red_NS')  # Transition from Yellow_NS to Red_NS
                time.sleep(self.state_timings['Red_NS'])

                self.transition_to('Green_EW')  # Transition from Red_NS to Green_EW
                time.sleep(self.state_timings['Green_EW'])

                self.transition_to('Yellow_EW')  # Transition from Green_EW to Yellow_EW
                time.sleep(self.state_timings['Yellow_EW'])

                self.transition_to('Red_EW')  # Transition from Yellow_EW to Red_EW
                time.sleep(self.state_timings['Red_EW'])

                self.transition_to('Green_NS')  # Transition from Red_EW to Green_NS
                time.sleep(self.state_timings['Green_NS'])

        except KeyboardInterrupt:
            print("Simulation stopped by the user.")

if __name__ == "__main__":
    traffic_system = TrafficLightControlSystem()
    traffic_system.run_traffic_light_system()
