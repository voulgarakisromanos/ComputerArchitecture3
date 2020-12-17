# ComputerArchitecture3

# Αρχιτεκτονική Υπολογιστών Εργασία 3

# Βουλγαράκης Ρωμανός | Μουστάκας Βασίλειος-Παναγιώτης
# 9383 | 9424




# Ερώτημα 1
## 1.1 

### Dynamic power
Dynamic power είναι η κατανάλωση ενέργειας που προκύπτει από τη δραστηριότητα των λογικών πυλών της CPU, και οφείλεται στη φόρτιση και αποφόρτιση των πυκνωτών εντός τους.  
Ισχύει η σχέση: **P<sub>dyn</sub> = C&#8901;V<sup>2</sup>&#8901;f**

όπου V είναι η τάση λειτουργίας, f η συχνότητα του ρολογιού, και C η συνολική χωρητικότητα. 
 
### Leakage
Leakage είναι η κατανάλωση ενέργειας που οφείλεται στη διαρροή ρεύματος εντός των transistor. Το μέγεθος αυτής της κατανάλωσης εξαρτάται από τα γεωμετρικά χαρακτηριστικά των transistor, τις φυσικές τους ιδιότητες και την θερμοκρασία τους. Η γενική τάση είναι ότι το leakage αυξάνεται για μικρότερα transistors και υψηλότερες θερμοκρασίες. 


### Σύγκριση της επίδρασης δύο προγραμμάτων
Αν δεν χρησιμοποιηθούν τεχνικές gating και dynamic frequency scaling, το dynamic power δεν επηρεάζεται από το είδος του προγράμματος που τρέχει, καθώς όλες οι παράμετροι που το επηρεάζουν μένουν σταθερές. Αν χρησιμοποιηθούν τα παραπάνω, το dynamic power εξαρτάται από τη δομή του προγράμματος και το ενδεχόμενο χρήσης πολλαπλών πυρήνων.  Όσον αφορά το leakage, η κύρια παράμετρος που μπορεί να μεταβληθεί και να το επηρεάσει είναι η θερμοκρασία. Άρα για όσο περισσότερο χρόνο τρέχει ένα πρόγραμμα, τόσο ανεβαίνει η θερμοκρασία και άρα τόσο αυξάνεται το leakage.  

## 1.2
Υπάρχει περίπτωση ένας επεξεργαστής που καταναλώνει 40W να μας δώσει μεγάλυτερη διάρκεια μπαταρίας από τον επεξεργαστή που καταναλώνει 4W, με την προϋπόθεση ότι κλείνουμε τους επεξεργαστές μετά το πέρας της εκτέλεσης των προγραμμάτων. Έτσι, ο επεξεργαστή με κατανάλωση 40W θα εκτελέσει το πρόγραμμα γρηγορότερα και άρα μπορεί να έχει λιγότερες συνολικές απώλειες από το leakage. 

Το McPAT μας δίνει δεδομένα για την ισχύ που καταναλώνει ο επεξεργαστής αλλά όχι για τον χρόνο εκτέλεσης του προγράμματος. Συνεπώς, δεν γίνεται να υπολογιστούν οι συνολικές απώλειες σε κάθε περίπτωση.
## 1.3

Τα αποτελέσματα που προκύπτουν από την εκτέλεση του McPAT φαίνονται στον ακόλουθο πίνακα:
<table>
     <thead>
        <tr >
            <th > </th>
            <th >Xeon</th>
            <th >ARM A9</th>
        </tr>
    </thead>
    <tbody>
        <tr >
            <td >Total Leakage</td>
            <td >36.83 W</td>
            <td >0.109 W</td>
        </tr>
        <tr>
            <td >Runtime Dynamic</td>
            <td >72.91 W</td>
            <td >2.960 W</td>
        </tr>

   </tbody>
</table>

Ορίζοντας **Δt** το χρονικό διάστημα το οποίο απαιτείται για την εκτέλεση κάποιας εφαρμογής στον Xeon και με δεδομένο ότι ο ARM A9 χρειάζεται 40 φορές περισσότερο χρόνο για το πέρας της. Εξετάζωντας τις απώλειες στο πέρας της εφαρμογής για τον ARM A9 προκύπτει:<br/>

Ε<sub>Xeon</sub> = P<sub>dyn_Xeon</sub> &#8901;Δt &nbsp; + P<sub>leak_Xeon</sub> &#8901;40&#8901;Δt = 1546.11&#8901;Δt<br/>
Ε<sub>A9</sub>&nbsp;&nbsp;&nbsp; = P<sub>dyn_A9</sub> &#8901;40&#8901;Δt + P<sub>leak_A9</sub> &#8901;40&#8901;Δt &nbsp;&nbsp;&nbsp;= 7.32&#8901;Δt

Παρατηρούμε μία πολύ μεγάλη διαφορά η οποία οφείλεται στο γεγονός ότι το P<sub>leak_Xeon</sub> συνεχίζει να υπάρχει ακόμα και μετά το πέρας εκτέλεσης της εφαρμογής, αφού θεωρούμε δεδομένο από την εκφώνηση πως δεν διακόπτεται η λειτουργία του συστήματος μετά την ολοκλήρωση εκτέλεσης. Συμπεραίνουμε, λοιπόν, πως ο Xeon δεν μπορεί να είναι περισσότερο energy-efficient από τον ARM A9, παρά την διαφορά στην απόδοση.


# Ερώτημα 2

Peak Power             |  Total Power
:-------------------------:|:-------------------------:
![][ICS_PP] |  ![][ICS_TP]

Peak Power             |  Total Power
:-------------------------:|:-------------------------:
![][DCS_PP] |  ![][DCS_TP]

Peak Power             |  Total Power
:-------------------------:|:-------------------------:
![][CLS_PP] |  ![][CLS_TP]

Peak Power             |  Total Power
:-------------------------:|:-------------------------:
![][L2S_PP] |  ![][L2S_TP]

Peak Power             |  Total Power
:-------------------------:|:-------------------------:
![][ICA_PP] |  ![][ICA_TP]

Peak Power             |  Total Power
:-------------------------:|:-------------------------:
![][DCA_PP] |  ![][DCA_TP]

Peak Power             |  Total Power
:-------------------------:|:-------------------------:
![][L2A_PP] |  ![][L2A_TP]


### Energy-Delay Product
![](https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/Energy-Delay_Product.jpg)
![](https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/Sjeng_CPI.jpg)

## Πηγές πιθανών σφαλμάτων

Οι προβλέψεις του McPAT πιθανώς να περιέχουν σημαντικό σφάλμα λόγω ελλειπούς μοντελοποίησης, μοντελοποίησης πολύ υψηλού επιπέδου ή λόγω υποθέσεων για την υλοποίηση του επεξεργαστή, οι οποίες δε συνάδουν με το μοντέλο που προσομοιώνεται. Πιο συγκεκριμένα, το μοντέλο ισχύος του McPAT είναι αναλυτικό, όχι εμπειρικό, και άρα αγνοεί λεπτομέρειες της υλοποίησης για χάρη της ευελιξίας και της ταχύτητας. Ορισμένα παραδείγματα είναι:
1. Δυσκολία μοντελοποίησης λογικής ελέγχου.
2. Έλλειψη συγκεκριμένων macros. 
3. Το McPAT υποθέτει ότι κάθε εντολή απαιτεί δύο read ports, πράγμα που δεν είναι απαραίτητα αληθές καθώς κάποιες εντολές (immediate) χρειάζονται μόνο έναν καταχωρητή πέρα από το operand.
4. Τέλειο clock-gating and data-gating. 
5. Για μια δομή cache, το McPAT κάποιες φορές διπλασιάζει το εμβαδόν πυριτίου του στοιχείου, χωρίς να να αυξάνει την per access ενέργεια που καταναλώνει.
6. Πιθανώς κάποια προγραμματιστικά λάθη

Η χρήση δύο προγραμμάτων για την προσομοίωση διαφορετικών πτυχών της ίδιας CPU μπορεί να αποτελέσει πηγή σφάλματος, καθώς τα προγράμματα μπορεί να κάνουν αντικρουόμενες υποθέσεις. Ταυτόχρονα υπερδιπλασιάζεται και η πιθανότητα να επηρεάσει την προσομοίωση κάποιο bug.

# Βιβλιογραφία
https://www.samxi.org/papers/xi_hpca2015.pdf

[ICS_PP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/peak_power/ICS.jpg
[DCS_PP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/peak_power/DCS.jpg
[CLS_PP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/peak_power/CLS.jpg
[L2S_PP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/peak_power/L2CS.jpg
[DCA_PP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/peak_power/DCA.jpg
[ICA_PP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/peak_power/ICA.jpg
[L2A_PP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/peak_power/L2CA.jpg
[ICS_TP]:https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/total_power/ICS.jpg
[DCS_TP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/total_power/DCS.jpg
[CLS_TP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/total_power/CLS.jpg
[L2S_TP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/total_power/L2CS.jpg
[DCA_TP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/total_power/DCA.jpg
[ICA_TP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/total_power/ICA.jpg
[L2A_TP]: https://github.com/voulgarakisromanos/ComputerArchitecture3/blob/main/Plots/total_power/L2CA.jpg
