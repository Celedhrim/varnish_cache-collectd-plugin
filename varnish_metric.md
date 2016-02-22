Metrique Varnish

Varnish 3 :
  ```
tail -n+15 varnish_metric.md | awk -F "|" '{ print "\t\47"$3"\47: Stat(\""$5"\", \""$2"\", \""$6"\")," }'
  ```

Varnish 4 :
  ```
  tail -n+15 varnish_metric.md | awk -F "|" '{ print "\t\47"$4"\47: Stat(\""$5"\", \""$2"\",\""$6"\")," }'
  ```

| Intitulé | varnish 3 | varnish 4 | Graph | type |
| --------- | ---- | ---- | ---- |
|backend_conn_too_many|backend_busy|backend_busy|backend_traffic|derive|
|backend_conn_success|backend_conn|backend_conn|backend_traffic|derive|
|backend_conn_not_attempted|backend_unhealthy|backend_unhealthy|backend_traffic|derive|
|backend_conn_recycles|backend_recycle|backend_recycle|backend_traffic|derive|
|backend_conn_failures|backend_fail|backend_fail|backend_traffic|derive|
|backend_conn_reuses|backend_reuse|backend_reuse|backend_traffic|derive|
|backend_requests_made|backend_req|backend_req|backend_traffic|derive|
|backend_conn_retry|backend_retry|backend_retry|backend_traffic|derive|
|cache_hits|cache_hit|cache_hit|hit_rate|derive|
|cache_misses|cache_miss|cache_miss|hit_rate|derive|
|cache_hits_for_pass|cache_hitpass|cache_hitpass|hit_rate|derive|
|bytes_outstanding_transient|transient.g_bytes|transient.g_bytes|memory_usage|gauge|
|bytes_available_transient|transient.g_space|transient.g_space|memory_usage|gauge|
|bytes_outstanding_s0|s0.g_bytes|s0.g_bytes|memory_usage|gauge|
|bytes_available_s0|s0.g_space|s0.g_space|memory_usage|gauge|
|fetch_failed|fetch_failed|fetch_failed|bad|derive|
|http_header_overflows|losthdr|losthdr|bad|derive|
|backend_conn_not_attempted|backend_unhealthy|backend_unhealthy|bad|derive|
|thread_creation_failed|n_wrk_failed|threads_failed|bad|derive|
|backend_conn_too_many|backend_busy|backend_busy|bad|derive|
|threads_hit_max|n_wrk_max|threads_limited|bad|derive|
|session_accept_failures|accept_fail|sess_fail|bad|derive|
|sessions_dropped|client_drop|sess_drop|bad|derive|
|threads_destroyed|n_wrk_drop|threads_destroyed|bad|derive|
|length_of_session_queue|n_wrk_lqueue|thread_queue_len|bad|gauge|
|esi_parse_warnings|esi_warnings|esi_warnings|bad|derive|
|esi_parse_errors_|esi_errors|esi_errors|bad|derive|
|number_of_objects|n_object|n_object|objects|gauge|
|number_of_expired objects|n_expired|n_expired|expunge|derive|
|number_of_lru_nuked_objects|n_lru_nuked|n_lru_nuked|expunge|derive|
|cache_hits|cache_hit|cache_hit|request_rate|derive|
|cache_hits_for_pass|cache_hitpass|cache_hitpass|request_rate|derive|
|cache_misses|cache_miss|cache_miss|request_rate|derive|
|backend_conn_success|backend_conn|backend_conn|request_rate|derive|
|backend_conn_not_attempted|backend_unhealthy|backend_unhealthy|request_rate|derive|
|good_client_requests_received|client_req|client_req|request_rate|derive|
|total_passed_requests_seen|s_pass|s_pass|request_rate|derive|
|total_pipe_sessions_seen|s_pipe|s_pipe|request_rate|derive|
|sessions_accepted|client_conn|sess_conn|request_rate|derive|
|thread_creation_failed|n_wrk_failed|threads_failed|threads|derive|
|threads_hit_max|n_wrk_max|threads_limited|threads|derive|
|total_number_of_threads|n_wrk|threads|threads|gauge|
|threads_created|n_wrk_create|threads_created|threads|derive|
|threads_destroyed|n_wrk_drop|threads_destroyed|threads|derive|
|body_traffic|s_bodybytes|s_resp_bodybytes|transfer_rates|derive|
|header_traffic|s_hdrbytes|s_resp_hdrbytes|transfer_rates|derive|
|varnish_uptime|uptime|uptime|uptime|gauge|
|n_duplicate_bans_removed|n_ban_dups|bans_dups|vcl_and_bans|derive|
|n_new_bans_added|n_ban_add|bans_added|vcl_and_bans|derive|
|n_backends|n_backend|n_backend|vcl_and_bans|gauge|
|n_vcl_total|n_vcl|n_vcl|vcl_and_bans|derive|
|n_total_active bans|n_ban|bans|vcl_and_bans|gauge|
|n_old_bans_deleted|n_ban_retire|bans_deleted|vcl_and_bans|derive|
|n_objects_tested|n_ban_obj_test|bans_tested|vcl_and_bans|derive|
|n_vcl_discarded|n_vcl_discard|n_vcl_discard|vcl_and_bans|derive|
|n_vcl_available|n_vcl_avail|n_vcl_avail|vcl_and_bans|derive|
