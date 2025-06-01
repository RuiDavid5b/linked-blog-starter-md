 
 * ~~Update dataloader's parameters: num_workers to half the "SLURM_CPUS_ON_NODE" env variable and add prefetch;~~
* ~~Increase batch size to 512;~~
* ~~Add some weight decay to the optimizer;~~
* Sanity check: Print the attention matrix;
* Add last 2 validation samples to aim "Text" (either after each epoch or just at the end of the training);