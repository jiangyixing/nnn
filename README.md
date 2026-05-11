
(.venv) root@735f5acae43a:/# vllm serve /models/Qwen/Qwen3-8B-AWQ   --host 0.0.0.0   --port 80  --served-model-name qwen3:8b --tensor-parallel-size 2 --enable-prefix-caching --enable-chunked-prefill --max-model-len 32768 --performance-mode throughput --tool-call-parser qwen3_coder --enable-auto-tool-choice --reasoning-parser qwen3  --gpu-memory-utilization 0.2
(APIServer pid=1444) INFO 05-11 03:01:02 [utils.py:302] 
(APIServer pid=1444) INFO 05-11 03:01:02 [utils.py:302]        █     █     █▄   ▄█
(APIServer pid=1444) INFO 05-11 03:01:02 [utils.py:302]  ▄▄ ▄█ █     █     █ ▀▄▀ █  version 0.17.0
(APIServer pid=1444) INFO 05-11 03:01:02 [utils.py:302]   █▄█▀ █     █     █     █  model   /models/Qwen/Qwen3-8B-AWQ
(APIServer pid=1444) INFO 05-11 03:01:02 [utils.py:302]    ▀▀  ▀▀▀▀▀ ▀▀▀▀▀ ▀     ▀
(APIServer pid=1444) INFO 05-11 03:01:02 [utils.py:302] 
(APIServer pid=1444) INFO 05-11 03:01:02 [utils.py:238] non-default args: {'model_tag': '/models/Qwen/Qwen3-8B-AWQ', 'enable_auto_tool_choice': True, 'tool_call_parser': 'qwen3_coder', 'host': '0.0.0.0', 'port': 80, 'model': '/models/Qwen/Qwen3-8B-AWQ', 'max_model_len': 32768, 'served_model_name': ['qwen3:8b'], 'reasoning_parser': 'qwen3', 'tensor_parallel_size': 2, 'gpu_memory_utilization': 0.2, 'enable_prefix_caching': True, 'enable_chunked_prefill': True, 'performance_mode': 'throughput'}
(APIServer pid=1444) INFO 05-11 03:01:02 [model.py:531] Resolved architecture: Qwen3ForCausalLM
(APIServer pid=1444) INFO 05-11 03:01:02 [model.py:1554] Using max model len 32768
(APIServer pid=1444) INFO 05-11 03:01:02 [awq_marlin.py:162] The model is convertible to awq_marlin during runtime. Using awq_marlin kernel.
(APIServer pid=1444) INFO 05-11 03:01:02 [scheduler.py:231] Chunked prefill is enabled with max_num_batched_tokens=4096.
(APIServer pid=1444) INFO 05-11 03:01:02 [vllm.py:659] Performance mode set to 'throughput'.
(APIServer pid=1444) INFO 05-11 03:01:02 [vllm.py:747] Asynchronous scheduling is enabled.
(EngineCore_DP0 pid=1519) INFO 05-11 03:01:07 [core.py:101] Initializing a V1 LLM engine (v0.17.0) with config: model='/models/Qwen/Qwen3-8B-AWQ', speculative_config=None, tokenizer='/models/Qwen/Qwen3-8B-AWQ', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, tokenizer_revision=None, trust_remote_code=False, dtype=torch.float16, max_seq_len=32768, download_dir=None, load_format=auto, tensor_parallel_size=2, pipeline_parallel_size=1, data_parallel_size=1, disable_custom_all_reduce=False, quantization=awq_marlin, enforce_eager=False, enable_return_routed_experts=False, kv_cache_dtype=auto, device_config=cuda, structured_outputs_config=StructuredOutputsConfig(backend='auto', disable_fallback=False, disable_any_whitespace=False, disable_additional_properties=False, reasoning_parser='qwen3', reasoning_parser_plugin='', enable_in_reasoning=False), observability_config=ObservabilityConfig(show_hidden_metrics_for_version=None, otlp_traces_endpoint=None, collect_detailed_traces=None, kv_cache_metrics=False, kv_cache_metrics_sample=0.01, cudagraph_metrics=False, enable_layerwise_nvtx_tracing=False, enable_mfu_metrics=False, enable_mm_processor_stats=False, enable_logging_iteration_details=False), seed=0, served_model_name=qwen3:8b, enable_prefix_caching=True, enable_chunked_prefill=True, pooler_config=None, compilation_config={'level': None, 'mode': <CompilationMode.VLLM_COMPILE: 3>, 'debug_dump_path': None, 'cache_dir': '', 'compile_cache_save_format': 'binary', 'backend': 'inductor', 'custom_ops': ['none'], 'splitting_ops': ['vllm::unified_attention', 'vllm::unified_attention_with_output', 'vllm::unified_mla_attention', 'vllm::unified_mla_attention_with_output', 'vllm::mamba_mixer2', 'vllm::mamba_mixer', 'vllm::short_conv', 'vllm::linear_attention', 'vllm::plamo2_mamba_mixer', 'vllm::gdn_attention_core', 'vllm::kda_attention', 'vllm::sparse_attn_indexer', 'vllm::rocm_aiter_sparse_attn_indexer', 'vllm::unified_kv_cache_update', 'vllm::unified_mla_kv_cache_update'], 'compile_mm_encoder': False, 'compile_sizes': [], 'compile_ranges_split_points': [4096], 'inductor_compile_config': {'enable_auto_functionalized_v2': False, 'combo_kernels': True, 'benchmark_combo_kernel': True}, 'inductor_passes': {}, 'cudagraph_mode': <CUDAGraphMode.FULL_AND_PIECEWISE: (2, 1)>, 'cudagraph_num_of_warmups': 1, 'cudagraph_capture_sizes': [1, 2, 4, 8, 16, 24, 32, 40, 48, 56, 64, 72, 80, 88, 96, 104, 112, 120, 128, 136, 144, 152, 160, 168, 176, 184, 192, 200, 208, 216, 224, 232, 240, 248, 256, 272, 288, 304, 320, 336, 352, 368, 384, 400, 416, 432, 448, 464, 480, 496, 512], 'cudagraph_copy_inputs': False, 'cudagraph_specialize_lora': True, 'use_inductor_graph_partition': False, 'pass_config': {'fuse_norm_quant': False, 'fuse_act_quant': False, 'fuse_attn_quant': False, 'enable_sp': False, 'fuse_gemm_comms': False, 'fuse_allreduce_rms': False}, 'max_cudagraph_capture_size': 512, 'dynamic_shapes_config': {'type': <DynamicShapesType.BACKED: 'backed'>, 'evaluate_guards': False, 'assume_32_bit_indexing': False}, 'local_cache_dir': None, 'fast_moe_cold_start': True, 'static_all_moe_layers': []}
(EngineCore_DP0 pid=1519) WARNING 05-11 03:01:07 [multiproc_executor.py:945] Reducing Torch parallelism from 16 threads to 1 to avoid unnecessary CPU contention. Set OMP_NUM_THREADS in the external environment to tune this value as needed.
(EngineCore_DP0 pid=1519) INFO 05-11 03:01:07 [multiproc_executor.py:134] DP group leader: node_rank=0, node_rank_within_dp=0, master_addr=127.0.0.1, mq_connect_ip=172.17.0.4 (local), world_size=2, local_world_size=2
(Worker pid=1589) INFO 05-11 03:01:12 [parallel_state.py:1393] world_size=2 rank=0 local_rank=0 distributed_init_method=tcp://127.0.0.1:59259 backend=nccl
(Worker pid=1592) INFO 05-11 03:01:17 [parallel_state.py:1393] world_size=2 rank=1 local_rank=1 distributed_init_method=tcp://127.0.0.1:59259 backend=nccl
(Worker pid=1589) <frozen importlib._bootstrap_external>:1301: FutureWarning: The cuda.cudart module is deprecated and will be removed in a future release, please switch to use the cuda.bindings.runtime module instead.
(Worker pid=1592) <frozen importlib._bootstrap_external>:1301: FutureWarning: The cuda.cudart module is deprecated and will be removed in a future release, please switch to use the cuda.bindings.runtime module instead.
(Worker pid=1589) <frozen importlib._bootstrap_external>:1301: FutureWarning: The cuda.nvrtc module is deprecated and will be removed in a future release, please switch to use the cuda.bindings.nvrtc module instead.
(Worker pid=1592) <frozen importlib._bootstrap_external>:1301: FutureWarning: The cuda.nvrtc module is deprecated and will be removed in a future release, please switch to use the cuda.bindings.nvrtc module instead.
(Worker pid=1589) INFO 05-11 03:01:18 [pynccl.py:111] vLLM is using nccl==2.27.5
(Worker pid=1589) WARNING 05-11 03:01:18 [symm_mem.py:67] SymmMemCommunicator: Device capability 8.9 not supported, communicator is not available.
(Worker pid=1592) WARNING 05-11 03:01:18 [symm_mem.py:67] SymmMemCommunicator: Device capability 8.9 not supported, communicator is not available.
(Worker pid=1592) WARNING 05-11 03:01:18 [custom_all_reduce.py:165] Custom allreduce is disabled because your platform lacks GPU P2P capability or P2P test failed. To silence this warning, specify disable_custom_all_reduce=True explicitly.
(Worker pid=1589) WARNING 05-11 03:01:18 [custom_all_reduce.py:165] Custom allreduce is disabled because your platform lacks GPU P2P capability or P2P test failed. To silence this warning, specify disable_custom_all_reduce=True explicitly.
(Worker pid=1592) INFO 05-11 03:01:18 [parallel_state.py:1715] rank 1 in world size 2 is assigned as DP rank 0, PP rank 0, PCP rank 0, TP rank 1, EP rank N/A, EPLB rank N/A
(Worker pid=1589) INFO 05-11 03:01:18 [parallel_state.py:1715] rank 0 in world size 2 is assigned as DP rank 0, PP rank 0, PCP rank 0, TP rank 0, EP rank N/A, EPLB rank N/A
(Worker pid=1592) INFO 05-11 03:01:18 [base.py:106] Offloader set to NoopOffloader
(Worker pid=1589) INFO 05-11 03:01:18 [base.py:106] Offloader set to NoopOffloader
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:18 [gpu_model_runner.py:4255] Starting to load model /models/Qwen/Qwen3-8B-AWQ...
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:19 [cuda.py:405] Using FLASH_ATTN attention backend out of potential backends: ['FLASH_ATTN', 'FLASHINFER', 'TRITON_ATTN', 'FLEX_ATTENTION'].
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:19 [flash_attn.py:587] Using FlashAttention version 2
Loading safetensors checkpoint shards:   0% Completed | 0/2 [00:00<?, ?it/s]
Loading safetensors checkpoint shards:  50% Completed | 1/2 [00:00<00:00,  1.10it/s]
Loading safetensors checkpoint shards: 100% Completed | 2/2 [00:01<00:00,  1.55it/s]
Loading safetensors checkpoint shards: 100% Completed | 2/2 [00:01<00:00,  1.46it/s]
(Worker pid=1589) (Worker_TP0 pid=1589) 
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:21 [default_loader.py:293] Loading weights took 1.39 seconds
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:21 [gpu_model_runner.py:4338] Model loading took 2.85 GiB memory and 2.410772 seconds
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:24 [decorators.py:465] Directly load AOT compilation from path /root/.cache/vllm/torch_compile_cache/torch_aot_compile/b7ef96e5642b8f7f10de1b5f506b0fc4d829e151d84f641ca40d0190f24d3758/rank_0_0/model
(Worker pid=1592) (Worker_TP1 pid=1592) INFO 05-11 03:01:24 [decorators.py:465] Directly load AOT compilation from path /root/.cache/vllm/torch_compile_cache/torch_aot_compile/b7ef96e5642b8f7f10de1b5f506b0fc4d829e151d84f641ca40d0190f24d3758/rank_1_0/model
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:24 [backends.py:916] Using cache directory: /root/.cache/vllm/torch_compile_cache/bed6aec13f/rank_0_0/backbone for vLLM's torch.compile
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:24 [backends.py:976] Dynamo bytecode transform time: 2.69 s
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:26 [backends.py:266] Directly load the compiled graph(s) for compile range (1, 4096) from the cache, took 1.445 s
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:26 [monitor.py:35] torch.compile takes 4.63 s in total
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:28 [gpu_worker.py:424] Available KV cache memory: 4.89 GiB
(EngineCore_DP0 pid=1519) INFO 05-11 03:01:28 [kv_cache_utils.py:1314] GPU KV cache size: 71,152 tokens
(EngineCore_DP0 pid=1519) INFO 05-11 03:01:28 [kv_cache_utils.py:1319] Maximum concurrency for 32,768 tokens per request: 2.17x
Capturing CUDA graphs (mixed prefill-decode, PIECEWISE): 100%|██████████| 51/51 [00:09<00:00,  5.41it/s]
Capturing CUDA graphs (decode, FULL): 100%|█████████████████████████████| 51/51 [00:08<00:00,  6.29it/s]
(Worker pid=1589) (Worker_TP0 pid=1589) INFO 05-11 03:01:46 [gpu_model_runner.py:5360] Graph capturing finished in 18 secs, took 1.65 GiB
(EngineCore_DP0 pid=1519) INFO 05-11 03:01:46 [core.py:282] init engine (profile, create kv cache, warmup model) took 24.53 seconds
(EngineCore_DP0 pid=1519) INFO 05-11 03:01:47 [vllm.py:659] Performance mode set to 'throughput'.
(EngineCore_DP0 pid=1519) INFO 05-11 03:01:47 [vllm.py:747] Asynchronous scheduling is enabled.
(APIServer pid=1444) INFO 05-11 03:01:47 [api_server.py:495] Supported tasks: ['generate']
(APIServer pid=1444) INFO 05-11 03:01:47 [parser_manager.py:202] "auto" tool choice has been enabled.
(APIServer pid=1444) WARNING 05-11 03:01:47 [model.py:1355] Default vLLM sampling parameters have been overridden by the model's `generation_config.json`: `{'temperature': 0.6, 'top_k': 20, 'top_p': 0.95}`. If this is not intended, please relaunch vLLM instance with `--generation-config vllm`.
(APIServer pid=1444) INFO 05-11 03:01:47 [parser_manager.py:202] "auto" tool choice has been enabled.
(APIServer pid=1444) INFO 05-11 03:01:47 [serving.py:185] Warming up chat template processing...
(APIServer pid=1444) INFO 05-11 03:01:47 [hf.py:318] Detected the chat template content format to be 'string'. You can set `--chat-template-content-format` to override this.
(APIServer pid=1444) INFO 05-11 03:01:47 [serving.py:210] Chat template warmup completed in 310.5ms
(APIServer pid=1444) INFO 05-11 03:01:47 [parser_manager.py:202] "auto" tool choice has been enabled.
(APIServer pid=1444) INFO 05-11 03:01:47 [api_server.py:500] Starting vLLM API server 0 on http://0.0.0.0:80
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:38] Available routes are:
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /openapi.json, Methods: GET, HEAD
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /docs, Methods: GET, HEAD
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /docs/oauth2-redirect, Methods: GET, HEAD
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /redoc, Methods: GET, HEAD
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /tokenize, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /detokenize, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /load, Methods: GET
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /version, Methods: GET
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /health, Methods: GET
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /metrics, Methods: GET
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /v1/models, Methods: GET
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /ping, Methods: GET
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /ping, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /invocations, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /v1/chat/completions, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /v1/chat/completions/render, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /v1/responses, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /v1/responses/{response_id}, Methods: GET
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /v1/responses/{response_id}/cancel, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /v1/completions, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /v1/completions/render, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /v1/messages, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /v1/messages/count_tokens, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /inference/v1/generate, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /scale_elastic_ep, Methods: POST
(APIServer pid=1444) INFO 05-11 03:01:47 [launcher.py:47] Route: /is_scaling_elastic_ep, Methods: POST
(APIServer pid=1444) INFO:     Started server process [1444]
(APIServer pid=1444) INFO:     Waiting for application startup.
(APIServer pid=1444) INFO:     Application startup complete.
