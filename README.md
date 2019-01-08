Usage: check_clickhouse -m <mode> [-w <warning>] [-c <critical>] [-h]

	-m <mode>	Mode tu run (see below)
	-w <warning>	Warning threshold (default depends on the mode, see below)
	-c <critical>	Critical threshold (default depends on the mode, see below)
	-h Display this help message

Supported modes:
	replication_log_delay: check difference between entry number in the log of general activity and entry number in the log of general activity that the replica copied to its execution queue for each table
		Default warning threshold: 5
		Default critical threshold: 10
	replication_future_parts: check number of data parts that will appear as the result of INSERTs or merges that haven't been done yet for each table
		Default warning threshold: 10
		Default critical threshold: 20
	replication_active_replicas: check number of healthly replicas for each table
		Default warning threshold: N/A
		Default critical threshold: N/A
	replication_parts_to_check: check number of data parts in the queue for verification for each table
		Default warning threshold: 5
		Default critical threshold: 10
	replication_is_readonly: check if any replica is in read-only mode
		Default warning threshold: N/A
		Default critical threshold: N/A
	replication_inserts_in_queue: check number of inserts of blocks of data that need to be made for each table
		Default warning threshold: 5
		Default critical threshold: 10
	replication_total_replicas: check total number of replicas known for each table
		Default warning threshold: 2
		Default critical threshold: 2
	replication_queue_size: check queue size for operations waiting to be performed for each table
		Default warning threshold: 10
		Default critical threshold: 20
	replication_is_session_expired: check if any replica has session with ZooKeeper expired
		Default warning threshold: N/A
		Default critical threshold: N/A




thanks https://github.com/yorick1989 for ur help
