- values added to [[context]] to be referenced in an [[expression]] by an [[expression/author]] that are provided/modified directly by the [[expression/caller]].
- all values provided by the [[expression/caller]] are implicitly [[signed data]] as they originate from a [[signed transaction]] signed by the [[expression/caller]] (by definition).
- it is the responsibility of the [[interpreter/calling contract]] to populate the [[context]] with relevant [[context/caller]] values, commonly taken directly from the [[calldata]] somehow
	- unlike [[context/signed]] there is no predefined format or convention for how [[context/caller]] values need to be provided to the [[interpreter/calling contract]], it's merely a conceptual distinction to realise that these values are only as [[trustworthy]] as the [[expression/caller]] themselves, which is to say that the [[expression/author]] should assume the values are arbitrarily manipulated/set by the [[expression/caller]] to get the best possible outcome for the [[expression/caller]] and aren't somehow true or fair representations of reality or some higher good
	- one example of [[context/caller]] is the [[interpreter/calling contract/flow]] id value that the [[expression/caller]] provides when they want to trigger a [[interpreter/calling contract/flow]]. If the id was supposed to represent some NFT id then the [[expression/author]] MUST check the [[word/erc721-balance-of]] the [[expression/caller]] in the [[expression]] to [[word/ensure]] that the [[expression/caller]] isn't simply lying about holing the NFT.