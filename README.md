# NixOS Configuration

This repository hosts my personal NixOS configuration files, primarily designed for my laptops. 


## Getting Started

### Prerequisites

Ensure you have NixOS installed on your system. This configuration is intended for use with NixOS and the Nix package manager.

### Installation

1. **Clone the Repository**

    Begin by cloning this repository to your local system:

    ```bash
    git clone https://github.com/apricotflute/nixos_config.git 
    ```


3. **Create a User-Specific Configuration**

    Add a `user-config.nix` in your `/etc/nixos/` directory with your user-specific settings. You could use this template provided below as a guide:

    ```nix
    { config, pkgs, ... }: {

      users.users.youruser = {
        isNormalUser = true;
        description = "youruser";
        extraGroups = [ "wheel", "networkmanager" ]; # Example groups
        packages = with pkgs; [
          # User-specific packages here
        ];
      };

      # Add any other user-specific configurations as needed

    }
    ```

    Replace `"youruser"` and the group list with your desired username and groups. Customize the packages as per your requirements.

4. **Apply the Configuration**
    
    To apply these configurations to your NixOS system, you'll need to incorporate them into your system's /etc/nixos/ directory. 
    
    Then apply the configuration changes by running:

    ```bash
    sudo nixos-rebuild switch
    ```

## Customizing Your Configuration

- Modify the `configuration.nix` for system-wide settings.
- The `user-config.nix` is intended for personal use and should not be tracked in this repository (already included in `.gitignore`).
- For detailed customization, refer to the [NixOS manual](https://nixos.org/manual/nixos/stable/).

## Contributing

Feel free to fork this repository and submit pull requests 
