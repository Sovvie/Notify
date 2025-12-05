A small, light weight, notification library.
Uses buffer encoding and tokenization for networking of notification data.

# [DOWNLOAD](https://cdn.discordapp.com/attachments/1373683745890242743/1373683777124962304/8qGEvIV.rbxm?ex=6933a2f6&is=69325176&hm=ee2bc26e5a86375e7497d16513d7a773f67d4e3d5cd088a67bee846463dfff4b&)

##    Key Features:
    - State-based notifications (Ok, Good, Bad, etc.)
    - Color theming, caching, and tokening
    - Notification tokening/naming
    - Multiple notification pipelines/sub-notification channels
    - Client-side event listeners
    - Cache/token hydration

##        Type:
        - Packet = { Message: string, State: number?, Pipeline: string?, Color3: Color3? }

##    Server API:
    - Send(name, packet) - Broadcast to all clients
    - SendClient(player, name, packet) - Send to specific client

##      Client API:
    - ListenTo(name: string, handler: func<packet>) - Register callback to a specific notification receiving all information pertaining to the sent notification.
    - Await(notify: string, state: enum?) -> Promise<dict<packet>> - Asynchronously wait for a specific notification and state
        - Await(notify: { string }, state: { number }) -> Promise<dict<packet>> - Asynchronously wait for a specific notification and pipeline, as well as one of many states.
    - State(index) - Convert state enum to string

##    State Enums:
    0: Ok         3: Positive
    1: Good     4: Negative  
    2: Bad       5: Success
                        6: Error
                        7: Alert
