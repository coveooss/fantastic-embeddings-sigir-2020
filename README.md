# Fantastic Embeddings and How to Align Them: Zero-Shot Inference in a Multi-Shop Scenario
_Public Data Release 1.1.0_


### Overview
This repo contains the description of the data released together with our _SIGIR eCom 2020_ 
paper [Fantastic Embeddings and How to Align Them: Zero-Shot Inference in a Multi-Shop Scenario](https://arxiv.org/abs/2007.14906).

### Data Download

The dataset is available for _research and educational_ purposes at this [page](https://www.coveo.com/en/ailabs/embeddings-and-how-to-align-them-zero-shot-inference-in-a-multi-shop-scenario).
To obtain the dataset, you are required to fill a form with information about you and your institution, and
agree to the _Terms And Conditions_ for fair usage of the data.

For convenience, _Terms And Conditions_ are also included in a pure `txt` format in this repo: 
usage of the data implies the acceptance of these _Terms And Conditions_.

### Data Structure

The dataset is provided in five files inside a `zip` archive:
 
* a `json` file, structured as list of lists. Each list contains a cross-shop session, that is, a shopping session initiated on *Shop A*
and terminated on *Shop B* (and vice versa); items in each list are ordered chronologically, and they all have the syntax `SHOP1_SKU41`, that is
an identifier of the shop (hashed) first, followed by `_` and a hashed identifier of the product the shopper interacted with. A sample
`json` file is provided in this repo: cross-shop session `["SHOP1_SKU21", "SHOP1_SKU32", "SHOP2_SKU13"]` means that an anonymous
shopper interacted with products `21` and `32` on the first shop, then browsed to the second shop and interacted with `13`. Please remember that
each shop has a different identifier policy, which makes the aligning problem interesting. The cross-shop dataset contains a total
of 12 259 sessions;
* two `json` files, labelled `original_vectors`, one for each shop: 
they contain a map between product identifiers (hashed in the same way as in the cross-shop dataset)
and related product embeddings _as trained separately for each shop_ (a previous release included a `pickle` file - versions >= _1.1.0_ are the recommended versions);
* two `json` files, labelled `aligned_vectors`, one for each shop: 
they contain a map between product identifiers 
and related product embeddings, _after the alignment proposed in the [paper](https://arxiv.org/abs/2007.14906)_.


We refer the reader to the original work for an extended explanation 
of the alignment problem. Usage of this data implies the acceptance of the _Terms And Conditions_ as set forward in
the [download page](https://www.coveo.com/en/ailabs/embeddings-and-how-to-align-them-zero-shot-inference-in-a-multi-shop-scenario).

### Contacts

For questions about the [paper](https://arxiv.org/abs/2007.14906) or the dataset, 
please reach out to [Jacopo Tagliabue](https://www.linkedin.com/in/jacopotagliabue/).

### Acknowledgments
The original paper is a collaboration between industry and academia, over a dataset gently provided by [Coveo](https://coveo.com/en/ailabs/embeddings-and-how-to-align-them-zero-shot-inference-in-a-multi-shop-scenario).
The authors of the paper are:

* [Federico Bianchi](https://www.linkedin.com/in/federico-bianchi-3b7998121/) - Postdoctoral Researcher at Università Bocconi
* [Jacopo Tagliabue](https://www.linkedin.com/in/jacopotagliabue/) - Coveo AI Labs
* [Bingqing Yu](https://www.linkedin.com/in/bingqing-christine-yu/) - Coveo
* [Luca Bigon](https://www.linkedin.com/in/bigluck/) - Coveo
* [Ciro Greco](https://www.linkedin.com/in/cirogreco/) - Coveo AI Labs

The authors wish to thank Richard Tessier and Coveo's legal team for supporting our research and believing in 
this data sharing initiative.

### How to Cite our Work

If you make use of this dataset, please cite our work:

```
@inproceedings{BianchiSIGIReCom2020,
  title = {Fantastic Embeddings and How to Align Them: Zero-Shot Inference in a Multi-Shop Scenario},
  author = {Bianchi, Federico and Tagliabue, Jacopo and Yu, Bingqing and Bigon, Luca and Greco, Ciro},
  url = {https://arxiv.org/abs/2007.14906},
  booktitle = {Proceedings of the SIGIR 2020 eCom workshop, July 2020, Virtual Event, published at
http://ceur-ws.org (to appear)},
  year = {2020}
}
```

