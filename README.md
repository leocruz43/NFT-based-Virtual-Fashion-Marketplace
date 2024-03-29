# NFT-based-Virtual-Fashion-Marketplace
创建一个基于NFT的虚拟时尚市场，设计师可以出售独特的数字服装和配饰。
# Simulating a basic NFT-based Virtual Fashion Marketplace

# This is a simplified simulation and does not interact with a real blockchain or smart contract.

class NFT:
    def __init__(self, title, designer, price):
        self.title = title
        self.designer = designer
        self.price = price
        self.owner = designer
        self.is_for_sale = True

class Marketplace:
    def __init__(self):
        self.nft_listings = []

    def mint_nft(self, title, designer, price):
        new_nft = NFT(title, designer, price)
        self.nft_listings.append(new_nft)
        print(f"NFT '{title}' minted successfully and listed by {designer}.")

    def show_listings(self):
        print("\nMarketplace Listings:")
        for nft in self.nft_listings:
            if nft.is_for_sale:
                print(f"Title: {nft.title}, Designer: {nft.designer}, Price: {nft.price} ETH")

    def buy_nft(self, title, buyer):
        for nft in self.nft_listings:
            if nft.title == title and nft.is_for_sale:
                nft.owner = buyer
                nft.is_for_sale = False
                print(f"{buyer} purchased {title} for {nft.price} ETH.")
                break
        else:
            print("NFT not found or not for sale.")

# Example usage
marketplace = Marketplace()

# Minting and listing NFTs
marketplace.mint_nft("Digital Dress", "Alice", 2)
marketplace.mint_nft("Virtual Hat", "Bob", 1)

# Show marketplace listings
marketplace.show_listings()

# Buying an NFT
marketplace.buy_nft("Digital Dress", "Carol")

# Show listings after purchase
marketplace.show_listings()
