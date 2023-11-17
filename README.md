# for generating taxonomic bar plots using feature_table_decon_all_1000.qza, GCMP_EMP_map_r29.txt, and silva_metaxa2_reference_taxonomy.qza
qiime feature-table group --i-table feature_table_decon_all_1000.qza --m-metadata-file GCMP_EMP_map_r29.txt --m-metadata-column host_scientific_name --p-mode median-ceiling --p-axis sample --o-grouped-table grouped-sample.qza
qiime taxa barplot --i-table grouped-sample.qza --i-taxonomy silva_metaxa2_reference_taxonomy.qza --o-visualization taxon_barplot.qzv
# for generating phylogenic analyses on qiime 2 after installing R packages and making input/output/procedure folders in your working directory:
 Rscript phylomorphospace_r14.r ../output/trait_table_reduced.txt ../input/huang_roy_molecular_r2.newick Sphingomonadales Bleaching_susceptibility_index
