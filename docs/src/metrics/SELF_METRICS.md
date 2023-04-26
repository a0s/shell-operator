# Metrics

* `shell_operator_hook_run_seconds{hook="", binding="", queue=""}` — a histogram with hook execution times. "hook" label is a name of the hook, "binding" is a binding name from configuration, "queue" is a queue name where hook is queued.
* `shell_operator_hook_run_errors_total{hook="hook-name", binding="", queue=""}` — this is the counter of hooks’ execution errors. It only tracks errors of hooks with the disabled `allowFailure` (i.e. respective key is omitted in the configuration or the `allowFailure: false` parameter is set). This metric has a "hook" label with the name of a failed hook.
* `shell_operator_hook_run_allowed_errors_total{hook="hook-name", binding="", queue=""}` — this is the counter of hooks’ execution errors. It only tracks errors of hooks that are allowed to exit with an error (the parameter `allowFailure: true` is set in the configuration). The metric has a "hook" label with the name of a failed hook.
* `shell_operator_hook_run_success_total{hook="hook-name", binding="", queue=""}` — this is the counter of hooks’ success execution. The metric has a "hook" label with the name of a succeeded hook.
* `shell_operator_hook_enable_kubernetes_bindings_success{hook=""}` — this gauge have two values: 0.0 if Kubernetes informers are not started and 1.0 if Kubernetes informers are successfully started for a hook.   
* `shell_operator_hook_enable_kubernetes_bindings_errors_total{hook=""}` — a counter of failed attempts to start Kubernetes informers for a hook. 
* `shell_operator_hook_enable_kubernetes_bindings_seconds{hook=""}` — a gauge with time of Kubernetes informers start.

* `shell_operator_tasks_queue_length{queue=""}` — a gauge showing the length of the working queue. This metric can be used to warn about stuck hooks. It has the "queue" label with the queue name.

* `shell_operator_task_wait_in_queue_seconds_total{hook="", binding="", queue=""}` — a counter with seconds that the task to run a hook elapsed in the queue.

* `shell_operator_live_ticks` — a counter that increases every 10 seconds. This metric can be used for alerting about an unhealthy Shell-operator. It has no labels.

* `shell_operator_kube_jq_filter_duration_seconds{hook="", binding="", queue=""}` — a histogram with jq filter timings.

* `shell_operator_kube_event_duration_seconds{hook="", binding="", queue=""}` — a histogram with kube event handling timings.

* `shell_operator_kube_snapshot_objects{hook="", binding="", queue=""}` — a gauge with count of cached objects (the snapshot) for particular binding.

* `shell_operator_kubernetes_client_request_result_total` — a counter of requests made by kubernetes/client-go library.

* `shell_operator_kubernetes_client_request_latency_seconds` — a histogram with latency of requests made by kubernetes/client-go library. 

* `shell_operator_tasks_queue_action_duration_seconds{queue_name="", queue_action=""}` — a histogram with measurements of low level queue operations. Use QUEUE_ACTIONS_METRICS="no" to disable this metric.

* `shell_operator_hook_run_sys_cpu_seconds{hook="", binding="", queue=""}` — a histogram with system cpu seconds.
* `shell_operator_hook_run_user_cpu_seconds{hook="", binding="", queue=""}` — a histogram with user cpu seconds.
* `shell_operator_hook_run_max_rss_bytes{hook="", binding="", queue=""}` — a gauge with maximum resident set size used in bytes.
