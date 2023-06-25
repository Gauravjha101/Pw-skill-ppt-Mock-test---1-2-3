Here's the solution to the "First Unique Character in a String" problem in JavaScript:
/**
 * Finds the index of the first non-repeating character in a string.
 * @param {string} s - The input string.
 * @returns {number} - The index of the first non-repeating character, or -1 if it doesn't exist.
 */
function firstUniqChar(s) {
  const charCount = new Map();

  // Count the occurrences of each character
  for (let i = 0; i < s.length; i++) {
    const char = s[i];
    charCount.set(char, (charCount.get(char) || 0) + 1);
  }

  // Find the first non-repeating character
  for (let i = 0; i < s.length; i++) {
    const char = s[i];
    if (charCount.get(char) === 1) {
      return i;
    }
  }

  return -1; // No non-repeating character found
}

// Test cases
console.log(firstUniqChar("leetcode")); // Output: 0
console.log(firstUniqChar("loveleetcode")); // Output: 2
console.log(firstUniqChar("aabb")); // Output: -1
