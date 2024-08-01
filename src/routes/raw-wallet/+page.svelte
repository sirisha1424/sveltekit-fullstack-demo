<script lang="ts">
    import { PrivateKey } from '@bsv/sdk'
    let WIF:string 
    let address:string

    function createKeys () {

        const privKey=PrivateKey.fromRandom()
        WIF=privKey.toWif()
        console.log("Private Key WIF format is",WIF)
        address=privKey.toAddress()
        console.log("Your bitcoin address is",address)
    }
</script>

<section>
    <button 
    on:click={createKeys}
    style="display: inline-block; padding: 10px 20px; margin: 20px 0; font-size: 16px; font-weight: bold; color: white; background-color: #007bff; border: none; border-radius: 5px; cursor: pointer; transition: background-color 0.3s;">
    Generate New Wallet Keys
</button>

<p style="font-size: 30px; margin: 10px 0;">
    <strong>Private Key WIF Format:</strong> {WIF}
</p>

<p style="font-size: 30px; margin: 10px 0;">
    <strong>Your Bitcoin Address:</strong> {address}
</p>
</section>