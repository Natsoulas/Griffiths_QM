# Griffiths Quantum Mechanics 3rd Edition
# Problem 1.13 Numerical Experiment Solultion
# Nicholas Natsoulas 08/10/2023
using Plots
using Random
# Construct histogram of randomly generated position data.

# Position of the oscillator at time t.
function x(t)
    return cos(t)
end

# Generate 10k random times within [0,2pi].
# Set seed.
Random.seed!(10545)
t_array = 2*π*rand(10000)
x_array = x.(t_array)

# Plot the histogram.
histo = histogram(x_array, bins=40, orientation=:vertical, 
        legend=false, xlabel="Position (x)", ylabel="Frequency", title="Histogram of Position Data")
# Define ρ(x) from problem 1.11 as a function.
function ρ(x)
    # Set all constants to 1.
    return 1/(sqrt(1-x^2))
end

# Re-define x_array to go between -1 and 1.
x_array = -1:0.001:1
ρ_array = ρ.(x_array)
# Plot the density function.
plot_rho = plot(x_array, ρ_array, title="Density Function", xlabel="Position", ylabel="Density", 
        label="Function Values", legend=:topright, marker=:circle, markersize=8, color=:blue)

display(plot_rho)
display(histo)
savefig(plot_rho,"density_function_plot.png")
savefig(histo,"position_histogram.png")

# They resemble eachother nicely!