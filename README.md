#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_SYSTEMS 10

typedef struct {
    char name[50];
    float temperature;
    float pressure;
    float fuelLevel;
    int srbsFailures;
    int electricalIssues;
    int mainEngineFailures;
} ShuttleSystem;

void displaySystemStatus(ShuttleSystem *system) {
    printf("System: %s\n", system->name);
    printf("Temperature: %.2f °C\n", system->temperature);
    printf("Pressure: %.2f kPa\n", system->pressure);
    printf("Fuel Level: %.2f %%\n", system->fuelLevel);
    printf("Solid Rocket Booster Failures: %d\n", system->srbsFailures);
    printf("Electrical System Issues: %d\n", system->electricalIssues);
    printf("Main Engine Failures: %d\n", system->mainEngineFailures);
    printf("-----------------------------\n");
}

void controlSystem(ShuttleSystem *system) {
    // Placeholder for controlling systems
    printf("Controlling system: %s\n", system->name);
    // Implement control logic here
}

void virtualManual() {
    printf("Virtual Manual:\n");
    printf("1. Check temperature and pressure regularly.\n");
    printf("2. In case of SRB failure, initiate backup procedures.\n");
    printf("3. For electrical issues, reset the electrical system.\n");
    printf("4. Monitor fuel levels closely to avoid depletion.\n");
    printf("-----------------------------\n");
}

int main() {
    ShuttleSystem shuttleSystems[MAX_SYSTEMS];
    int systemCount = 0;

    // Initialize shuttle systems
    strcpy(shuttleSystems[systemCount].name, "Main Shuttle System");
    shuttleSystems[systemCount].temperature = 25.0;
    shuttleSystems[systemCount].pressure = 101.3;
    shuttleSystems[systemCount].fuelLevel = 75.0;
    shuttleSystems[systemCount].srbsFailures = 0;
    shuttleSystems[systemCount].electricalIssues = 0;
    shuttleSystems[systemCount].mainEngineFailures = 0;
    systemCount++;

    // Add more systems as needed
    // ...

    // Display system status
    for (int i = 0; i < systemCount; i++) {
        displaySystemStatus(&shuttleSystems[i]);
    }

    // Control system example
    controlSystem(&shuttleSystems[0]);

    // Show virtual manual
    virtualManual();

    return 0;
}
