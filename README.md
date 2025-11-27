# HFF
Official implementation of "HFF?"

1) Convert the .pt ckpts into diffusers using convert_all_checkpoints.py
2) Generate safe data for sequential FT
3) Run SFT.py (for sequential FT)
4) Generate benchmark images via generate_benchmark_images_from_json.py (for testing before and after FT)
5) Evaluate benchmark using eval_benchmark.py (for NSFW scores)

🔒 From a Threat to a Complete Benchmark
Routine benign fine-tuning (BFT) can unintentionally weaken the safety alignment of text-to-image models. We turn this overlooked issue into a measurable robustness test, quantifying how much a model drifts toward harmful outputs after harmless updates.
To evaluate aligned T2I systems holistically, we introduce SPQR, a four-axis benchmark capturing safety, fidelity, quality, and stability.
🧩 Key Ideas
⚠️ Unintentional Attack: Measures harmfulness drift after benign fine-tuning.
📉 Δh Drift Score: Lower drift → higher robustness.
📊 Unified Benchmark: Evaluates Safety, Prompt-adherence, Quality, and Robustness.
🏆 SPQR Score: Harmonic mean of the four metrics for fair cross-model comparison.
🧭 SPQR Components
🛡️ Safety (S): Avoids harmful/explicit content.
📝 Prompt-Adherence (P): Follows the input prompt faithfully.
🎨 Quality (Q): Maintains high visual realism (normalized FID).
🔁 Robustness (R): Stays safe even after benign fine-tuning.
🏅 SPQR Formula
SPQR = 4 / (1/S + 1/P + 1/Q + 1/R)
A single score that reflects balanced, safety-aligned performance.
