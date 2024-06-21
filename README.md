# funcPtr-and-callBack

#include <stdio.h>

// Define a type for the callback function
// we need to define typedef for passing function as an argument to function
typedef void (*CallbackFunction)(int, char*);

// A function that takes a callback function as an argument
void process_data(int data, char* message, CallbackFunction callback) {
    // Do some processing on the data
    printf("Processing data: %d\n", data);

    // Call the callback function with the processed data and message
    callback(data, message);
}

// A callback function that will be passed to process_data
void my_callback(int data, char* message) {
    printf("Callback received: %d, %s\n", data, message);
}

int main() {
    // Create a callback function pointer
    CallbackFunction callback = my_callback;

    // Call process_data with the callback function
    process_data(42, "Hello, world!", callback);

    return 0;
}
