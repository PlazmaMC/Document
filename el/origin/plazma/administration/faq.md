---
description: Μάθετε σχετικά με συχνές ερωτήσεις.
---

# ⁉️ Συχνές Ερωτήσεις

{% hint style="info" %}

**Δεν μπορείτε να βρείτε την απάντηση που ψάχνετε;**

[Επίσημος Διακομιστής Discord](https://discord.gg/MmfC52K8A8) ή συζητήσεις στο [GitHub](https://github.com/PlazmaMC/PlazmaBukkit/discussions) για να ρωτήσετε την κοινότητα!

{% endhint %}

### Το Plazma δεν ξεκινά

Εάν εμφανίζεται το μήνυμα `no main manifest attribute, in plazma-(version).jar`,\
το αρχείο που κατεβάσατε είναι αρχείο API ανάπτυξης, πρέπει να κατεβάσετε το **Reobf Paperweight** από τη σελίδα GitHub.

Για περισσότερες πληροφορίες, ανατρέξτε στην παρακάτω σελίδα.

{% content-ref url="getting-started/" %}
[getting-started](getting-started#id-2)
{% endcontent-ref %}

### Εμφανίζεται προειδοποίηση κάθε φορά που ξεκινά ο διακομιστής

Το Plazma περιλαμβάνει ορισμένα ασταθή patches και μπορεί πάντα να προκαλέσει δυσλειτουργίες, γι' αυτό εμφανίζει το ακόλουθο μήνυμα προειδοποίησης κάθε φορά που ο διακομιστής ξεκινά.

```log
[12:34:56 WARN]: Warning! Plazma may cause unexpected problems, so be sure to test it thoroughly before using it on a public server.
```

Μπορείτε να απενεργοποιήσετε το συγκεκριμένο μήνυμα προειδοποίησης χρησιμοποιώντας την ιδιότητα συστήματος [`-DPlazma.iKnowWhatIAmDoing`](#user-content-fn-1)[^1].

Για περισσότερες πληροφορίες, ανατρέξτε στην παρακάτω σελίδα.

{% content-ref url="reference/arguments.md" %}
[arguments.md](reference/arguments.md#plazma.iknowwhatiamdoing)
{% endcontent-ref %}

***

[^1]: Διαθέσιμο από την έκδοση 1.20.1
