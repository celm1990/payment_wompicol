# Wompi Colombia Payment Acquirer

This is an implementation of the [Wompi](https://wompi.co/) payment acquirer/gateway for Odoo, in the form of web checkout, as specified in the [documentation](https://docs.wompi.co/docs/en/widget-checkout-web).

## STATUS: WIP

### Progress

This are the check list to implement Wompi.

- [x] What is the private key used for?
    NOTE: To use the api integration, but also to check on the state of a transaction.
- [x] Url for prod and testing
- [x] Wompi controller with different url for testing.
    - [ ] Implement a way for the methods to know if a test Transaction
- [x] Key formatting per environment NOTE: Wompi doesn't format the keys, It just had completely different keys. So two new fields must be created to deal with this.
- [x] Values required by Wompi
- [x] ResponseUrl, process when It's client GET and not wompi api POST.
    - [ ] Test
- [ ] Controller method on response url
    - [ ] Payment Transaction methods to process Wompi events.
        - [x] Instruction to what url for events to set on the wompi console.
            - [ ] Test if on change of the base url, test and prod url also changes in the config.
        - [x] _wompicol_form_get_tx_from_data process the data from the acquirer and validates, a transaction exists, if exists it's returned, if more than one or none are found, error out.
        - [x] _wompicol_form_get_invalid_parameters: Returns invalid parameters sent from the payment acquirer or a fake request, ant the parent class takes care of logging it.
        - [x] _wompicol_form_validate takes care of setting the transaction state from the received data given it passes the invalid_parameters method.
        - [ ] Call wompi api to check if the event is actually true.
        - [ ] Test
- [ ] Tests

## License MIT
