# trial-1
trial 1
def am_i_hungry(request):
    if request["hunger_level"] > 5:
        return True
    else:
        return False
def is_it_lunch_time(request):
    if request["time_in_hours_now"] > 12:
        return True
    else:
        return False
def time_elapsed_since_last_ate(request):
    if request["time_in_hours_now"] - request["last_ate_at"] > 4:
        return True
    else:
        return False
def time_is_right(request):
    if is_it_lunch_time(request) or time_elapsed_since_last_ate(request):
        return True
    else:
        return False
def time_to_eat_lunch(request):
    if time_is_right(request) and am_i_hungry((request)):
        return True
    else:
        return False
# example: not hungry enough
outcome_1 = time_to_eat_lunch({"hunger_level": 4, "time_in_hours_now": 14, "last_ate_at": 9})
print(outcome_1)
# example: too soon and not lunch-time
outcome_2 = time_to_eat_lunch({"hunger_level": 48, "time_in_hours_now": 11, "last_ate_at":10})
print(outcome_2)
# example: just right
outcome_3 = time_to_eat_lunch({"hunger_level": 6, "time_in_hours_now": 14, "last_ate_at": 9})
print(outcome_3)
