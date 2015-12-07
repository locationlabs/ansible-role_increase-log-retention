This role attempts to fix the ubuntu default logrotate settings, which tend to lose log data after
somewhere between 4 and 7 days.  It changes the default log rotation settings to use date
extension, keep 999 files, rotate at 20MBytes/file, and compress (with delay).

The packages which are currently affected are very basic: apt, dpkg, rsyslog, upstart

Role inputs:
- size_limit: string in a format understood by logrotate, defaults to '20M'
- rotate_count: int, number of rotations to keep, defaults to 999
