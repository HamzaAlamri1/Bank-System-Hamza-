class BankSecuritySystem:
    def __init__(self):
        self.authorized_users = ['user1', 'user2', 'admin']
        self.security_alerts = []

    def login(self, username, password):
        # Simulating authentication process
        if username in self.authorized_users and password == 'password123':
            print("Login successful.")
            self.check_security_level(username)
        else:
            print("Invalid credentials. Login failed.")

    def check_security_level(self, username):
        # Simulating security level check
        security_level = self.get_security_level(username)

        if security_level == 'high':
            print("High-security measures activated.")
            self.monitor_activity(username)
        elif security_level == 'medium':
            print("Medium-security measures activated.")
        else:
            print("Low-security measures activated.")

    def get_security_level(self, username):
        # Simulating retrieving security level from a database
        # In a real system, this would involve more complex logic and data retrieval
        if username == 'admin':
            return 'high'
        elif username == 'user1':
            return 'medium'
        else:
            return 'low'

    def monitor_activity(self, username):
        # Simulating monitoring user activity for suspicious behavior
        for _ in range(5):
            transaction_amount = float(input("Enter transaction amount: "))
            if transaction_amount > 1000:
                self.security_alerts.append(f"Suspicious transaction by {username}. Amount: {transaction_amount}")
                print("Security alert: High-value transaction detected.")
            else:
                print("Transaction successful.")

    def display_security_alerts(self):
        print("Security Alerts:")
        for alert in self.security_alerts:
            print(alert)


# Example usage:
bank_system = BankSecuritySystem()
bank_system.login('user1', 'password123')
bank_system.login('admin', 'password123')
bank_system.login('invalid_user', 'wrong_password')

# Display security alerts (simulated)
bank_system.display_security_alerts()
