## Redis - Base de Datos clave-valor


def nuevo_following(username, following_username, timestamp):
    if username == following_username:
        print('ERROR: Username and following username are the same')
        return False
    if not redis_db.get(username):
        print('ERROR: User ' + username + ' does not exist')
        return False
    if not redis_db.get(following_username):
        print('ERROR: User ' + following_username + ' does not exist')
        return False

    user_id = redis_db.mget(username)[0]
    following_id = redis_db.mget(following_username)[0]

    _id = 'followings:{0}'.format(user_id)

    following_data = {}
    following_data[following_username] = timestamp
    redis_db.zadd(_id, following_data)
    
    return following_data