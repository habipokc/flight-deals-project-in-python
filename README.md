# flight-deals-project-in-python
This script fetches destination data from a Google Sheet using the data_manager object from the data_manager.py module. The data includes the city name, maximum price, and an empty field for the IATA code of the destination airport.

If the IATA code is missing for a destination, the script uses the flight_search object from the flight_search.py module to fetch the IATA code of the destination airport from the Flight Search API. It then updates the destination_data list in data_manager with the newly retrieved IATA code for the corresponding destination.

Next, the script searches for flights from the "LND" (London) airport to each destination in the destination_data list, using the flight_search.check_flights() method. The search checks for flights departing on or after the current day and returning up to six months later.

Finally, the flight_search.check_flights() method returns the cheapest available flight for the given route and time period, and the script prints the result.

This script is designed to be used in conjunction with a Google Sheet that stores destination data and is updated with the corresponding IATA codes using the flight_search object. The script can be run periodically to keep the Google Sheet up-to-date with the latest flight prices and availability.
