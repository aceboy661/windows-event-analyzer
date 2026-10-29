from datetime import datetime

def detect_failed_logons(log_file):
    failed_count = 0
    failed_entries = []

    try:
        with open(log_file, "r") as file:
            for line in file:
                if "4625" in line or "Failed logon" in line:
                    failed_count += 1
                    failed_entries.append(line.strip())

        print("=" * 55)
        print("WINDOWS FAILED LOGON DETECTION REPORT")
        print(f"Scan Time: {datetime.now().strftime('%Y-%m-%d %H:%M:%S')}")
        print("=" * 55)

        if failed_entries:
            print("\nDetected Failed Logon Events:\n")
            for entry in failed_entries:
                print(f"- {entry}")

        print("\n" + "-" * 55)
        print(f"Total Failed Logon Events: {failed_count}")

        if failed_count >= 4:
            print("ALERT: Possible brute-force or password spray detected!")
            print("Recommendation: Check source IPs and targeted accounts.")
        else:
            print("Status: Some failed logons found or none.")

        print("=" * 55)

    except FileNotFoundError:
        print("Error: Log file not found.")

detect_failed_logons("logs/sample_windows_security.log")
