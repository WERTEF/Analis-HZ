# Analis-HZ
Analisator HZ
# Code for Frequency Spectrum Analyzer using FFT
import numpy as np
import matplotlib.pyplot as plt
from scipy.io import wavfile

def analyze_frequency_spectrum(audio_file_path):
    # Read the audio file
    sample_rate, audio_data = wavfile.read(audio_file_path)

    # Perform FFT (Fast Fourier Transform)
    spectrum = np.fft.fft(audio_data)

    # Calculate the frequency values
    frequencies = np.fft.fftfreq(len(spectrum), 1 / sample_rate)

    # Plot the frequency spectrum
    plt.plot(frequencies, np.abs(spectrum))
    plt.title("Frequency Spectrum")
    plt.xlabel("Frequency (Hz)")
    plt.ylabel("Amplitude")
    plt.show()

# Example usage
audio_file_path = "path/to/your/audio.wav"
analyze_frequency_spectrum(audio_file_path)
