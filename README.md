# x-user-cron
import os
from dotenv import load_dotenv
from x_api import get_user_info
from storage import save_daily_log

load_dotenv()

def main():
    username = os.getenv("TARGET_USERNAME")
    user_data = get_user_info(username)
    save_daily_log(user_data)
    print("データ保存完了:", user_data)

if __name__ == "__main__":
    main()
