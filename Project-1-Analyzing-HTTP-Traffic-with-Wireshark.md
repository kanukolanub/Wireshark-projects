# Analyzing HTTP Traffic with Wireshark

## Introduction

In this project, we will use Wireshark to capture, filter and analyze HTTP traffic. HTTP traffic analysis is crucial for understanding web communication, identifying potential security issues, and investigating anomalies in network traffic.

## Lab Set-up and Tools

1. **Tool**: Wireshark v4.2.6
2. **Web Browser**: Chrome for generating HTTP traffic.

## Exercises

### Exercise 1: Capture HTTP Traffic

#### Steps

1. Open Wireshark.
2. Select the network interface that connects to the internet.
3. Click on the "Start Capture" button (the blue shark fin icon).
4. Open your web browser and navigate to a website that uses HTTP (e.g., http://example.com).
5. Let the page load completely and then stop the capture in Wireshark by clicking on the red square icon.

#### Expected Output

- A capture file containing network traffic, including HTTP requests and responses.

![Screenshot 2024-08-03 120214](https://github.com/user-attachments/assets/dbfff9f7-992d-40eb-a93e-ec482f1a38f3)


### Exercise 2: Filter HTTP Traffic

#### Steps

1. In Wireshark, go to the filter bar at the top.
2. Enter the filter `http` and press Enter.
3. Wireshark will display only the HTTP traffic from the capture.

#### Expected Output

- Displayed HTTP traffic filtered from the overall capture.

![Screenshot 2024-08-03 152955](https://github.com/user-attachments/assets/d740c807-e6ea-45e5-b439-e416912cd872)

### Exercise 3: Analyze HTTP Requests

#### Steps

1. In the filtered HTTP traffic, locate an HTTP GET request.
2. Click on the GET request to view its details in the packet details pane.
3. Expand the "Hypertext Transfer Protocol" section to see detailed information about the request, such as the requested URL, headers, and parameters.

#### Expected Output

- Detailed information about an HTTP GET request displayed.

- ![Screenshot 2024-08-03 184405](https://github.com/user-attachments/assets/d32473dd-f07a-42d3-b721-e169cbbff1b3)

### Exercise 4: Analyze HTTP Responses

#### Steps

1. In the filtered HTTP traffic, locate the corresponding HTTP response for the GET request you analyzed.
2. Click on the response to view its details in the packet details pane.
3. Expand the "Hypertext Transfer Protocol" section to see detailed information about the response, such as the status code, headers, and content type.

#### Expected Output

- Detailed information about an HTTP response displayed.
  
![Screenshot 2024-08-03 184755](https://github.com/user-attachments/assets/432ea11c-7501-4813-b720-af413feaff96)

### Exercise 5: Extract and Examine Payload Data

#### Steps

1. In the HTTP response details, look for the payload data (e.g., HTML content).
2. Right-click on the response packet and select "Follow" > "TCP Stream" to view the entire HTTP conversation.
3. Examine the payload data in the TCP stream window to understand the content being transferred.

#### Expected Output

- Payload data from the HTTP response extracted and examined.

![Screenshot 2024-08-03 185014](https://github.com/user-attachments/assets/539afa33-82e1-4508-9ed5-7e3fc1d881df)
